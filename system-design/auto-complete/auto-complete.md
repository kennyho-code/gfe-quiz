# Requirements

- How many suggestions?
- does it need history of the user?
- when should autocomplete start?
- if it's more suggestions...should it scroll?
- image or dictation?

# Architecture

- Client
  - Controller
    - Input
    - DropDown
  - Client Store
    - History
- Server
- API
- Rendering Approach
- Render dynamically but...because it's a component

# Data

```
Search Results
{

    data: {
        results: [
            r1,
            r2,
            rN
        ]
    }
}

# History
{
    history: [
        {query, date}
    ]
}
```

# Interface

- Controller
  - talks to the server... has the data for search
  - handles responses for results
  - stores history for completed searches
  - Components
    - Input Component - handles onChange text
    - Drop Down Component - handles appearnce of results
- Server
- handles the requests...with the query and number of results
- how does search work under the hood?..... we can't use SQL...so there's sort of algorithm

# Optimization

- debouncing...`useDebounce` for a specific amount of time to prevent excessive requests calls
- no error states
- client side rendering...mostly dynamic ...server load is the bottle neck
- drop down...needs to render fast...so maybe some sort of virtualized list?
