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
- ## drop down...needs to render fast...so maybe some sort of virtualized list?

# Review

## Requirements

- used by different websies
- input field ui and results ui should be customizable
- results? text media, images?
- laptop, tablets, mobile...
- what type of devices?
- fuzzy search?

## Architecture

- input field ui
- results ui
- cache
- controller

## Data Model

- controller
  - props options exposted by component api
  - current search string
- cache
  - intital results
  - cache results

## Interface

- Client
- Basic Api
  - num results
  - api url
  - event listeners: input, focus, blur, change, select
  - customiszed rendering
    - theming options object
    - classNames
    - render function/callback
- Advanced API
  - minimum query length?
  - debounce duration (300ms?)
    -api timeout duration
  - cache-related
- Server API
  - query
  - limit
  - pagiation

## Optimizations

- network - handling concurrent requests/race conditions
  - 1. time stamp for latest requests
  - 2. keyed by query string only present results according to input value (better)
- save keystrokes in cache....as users and enter characters and backspace
- Failed requests and retries
  - automatic retry?...
- Offline usage
  - read purely from cache
  - don't fire any requests
  - ui indicator alert that there's no connection
- 1. Cache
  - hashmap with search query as key and resutls as value

```
const cache = {

  fa: [
      {type: 'organization', text: 'facebook},
    { type: 'text', text: 'face' },

  ],

  fac: [...],
  face: [..],
  facebook,
}

```

- 2. list of results... but is slow..because you would have to filter

3. Normalized requets - normalizr - ... have results like a db... with cache with keys to each result...u can reuse the data

```
const results = {
  1: { id: 1, type: 'organization', text: 'Facebook' },
  2: {
    id: 2,
    type: 'organization',
    text: 'FasTrak',
    subtitle: 'Government office, San Francisco, CA',
  },
  ...
}
const cache = {
  fa: [1, 2, 3],
  fac: [1, 3, 4],
  face: [1, 3, 5],
  faces: [6, 7, 8],
  // ...
};
```

- Which structure?
- short lived websites ... option 1 .. user doesn't stay on the site and isn't ofeten (google)
- long lived websites (facebook)...caching might be a memory hog though

Initial results

- popular search queries, historical searches, trending stocks...
- typeahead query

Caching Strategy

- space vs time
- when to evict?...how often things are updated ...means how often they should be evicted
- networy only vs cacche only
- cache duration..time to live

Performance

- loading speed ... depends on client side caching
- deobuncing/throttling ..prevent for overloading server
- memory usuage --- purging cache when browser is idle or too much memmory being used
- Virtualized list...only rendering what's in view....view only dom nodes when they are visible.

User Experience

- auto focus
- handdle different states - loading, error, no network
- handle long strings.... truncating or ellipsis .. or wrap

Mobile Friendliness

- result term should be tappable for user
- dynamic number depending on window size
- autocapitalize, autocomplete, autocorrect, spellcheck set to off

Typos in search

- Fuzzy search doing levenshtein distance

Query results positioning

- depending where it's most visible ... where is the input decides where are the results

Accessibility

- sematic html
- ul li .... role="listbox" .. "role="option"
- aria label for input
- role="combobox" for input
- aria-haspopup
- aria-expanded
- aria-autocomplete

Keyboard Interaction

- up and down arrows to get end of list
