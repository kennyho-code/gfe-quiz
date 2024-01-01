# Requirements

- what is the functionality of the app, to book a hotel or bnb... expedia does flights too ..but to keep it simple, the main thing is to book reservations at a hotel
- experience
  - (1) a user goes to a site...searches a destination, from date, to date. number of travelers
  - (2) sees a list of avaiable options...results
  - (3) chooses a result from the list
  - (4) goes to the details page
  - (5) confirms with payment
  - (6) done...submits a record to the database....with details of itenarary
- what is the flow like..different pages...or SPA?

# Architecture

We can divide the flow up with the requirements above

Client Flow

- Search Page
- Property List Page
- Property Details Page
- Property Payments Page
- Itenarary Done Page

Server Flow

- The user will contact a server with api endpoints
- Input Search Results of Destination Locations (city + country)
- Search Submit Results with List of Properties
- Submit Payment to Property which receives an intenarary

Static vs Dynamic

- Search results are dynamic and have to do a request...client side rendering must be used
- List pages also have to be dynamic because rooms is real time
- payment flow can use server side rendering
- payment flow is dynamic ...as it needs a request to submit...

Seems like a hybrid app might be the best...
a very complex app where there is static information concerning details about the property..but prices and #of reservations of do
client side rendering as it's dynamic

# Data Model

```

User {
    userDetails: UserDetails (just firstname lastName)
}

Property {
    propertyDetails: PropertyDetals (name, location)
}

Payment {
    user: User;
    property: User
    itenarary: Itenerary
}

Itenarary {
    user: User
    Property: Property,
    dateBooked,
    startTime,
    endTime
    payment: PAyment
}

```

# Interfaces

Pages
Search Page

- Form
  - Location Input with drop down search (hits api) with debounce of 300ms
  - From
  - To
  - number of travelers and rooms
- Hits Controllers...hits endpoint with query params `/properties?location{$location}&from=${from}&to=${to}&rooms-${rooms}&travelers=${travelers}`
- once submits... goes to Property details page
  - Controller that data in memory per page
  - Filter
  - List of Property Results with show more button

# Optimizations
