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
  - `GET` `/locations?query=${query}`
- Hits Controllers...hits endpoint with query params `GET` `/properties?location{$location}&from=${from}&to=${to}&rooms-${rooms}&travelers=${travelers}`
- once submits... goes to Property details page

  - Controller that data in memory per page
  - Filter
  - List of Property Results with show more button
  - pagination.... off set ....

  ```
  {
    pagination: {
      size: 10,
      page: 2,
      totalPages = 5;
      totalResults = 50;

    }

    results [
      property1,
      property2,
      ....
    ]
  }
  - Payment Form
    - Form
    - ..whose checking in ...
    - payment method form
    ... form of forms..
    - submit ... /payment ... with response body
  ```

```
POST /payment
    {
      customer: {

      },
      protection: {

      }
      payment: {

      }
    }

```

with response of

```
{
  ...details
  confirmation number
}

```

...goes to a new screen.

# Optimizations

- Search Locations
  - history cache
  - number of cities?.....
  - show more?
  - cache when backspacicng
  - look to auto-complete feature
- search button for GET /properties
  - optimistic loading when hovering over search button
  - loading information ...only above the fold
    - images
    - prices
    - ....we need "list virtualization" ..this is dynamic
  - filterating ...and other static ui's can be server side rendered
  - pages with long results can use pagination..via offset
  -
- Payment form
  - ....1 page with just bunch of input to reduce requests
  - autofill ..for common fields.. like email..payment info...etc..
  - server side rendering as it isn't dynamic
- Confirmation form
  - server side rendering...data comes from payment response...


# Research

## Requirements
Features
- search and browse accomodation listings
- view accomodiation details
- make reserveation for accomodations

Demographics

Non-Functional requirements

What Devices

Users have to be signed in?

Summary
- SEO
- Performance
- Internationalization
- Device support
- similar to E-commerce

## Architecture
- SSR is a must for SEO
- SPA (single-page app) or MPA (multi-page-app)
- SPA doesn't make sense cannot reuse the shell
- MPA might make sense as travel sites have very broad features
- Frameworks essential for maintaining client side code
- SSR for initial use... clientside after interaction (SSR with hydration) (use Next.js)
- airbnb, booking, expedia, tripAdvisor uses SSR and React

## Data Model






