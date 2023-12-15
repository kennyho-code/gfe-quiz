# News Feed

Design a news feed user interface similar to Facebook
RADIO

## Requirements

ask some questions...

- Where is it located? on a particular sites
- Do we have any existing components?
- Any similar features from other websites?
- how many of the "tweets" or "posts" do we have to get
- how is the loaded?...which endpoint?
- how does that data s tructure look?
- what is the interactivity?
- When we scroll down..is it infinite scroll or some sort of pagination?
- functional requirements?
- non-functional requirements?
- desktop and mobile experience?
- performanec requirements?
- main users of the feature?

## Architecture

- Would need some some sort of scroll component?
- how would it scroll...
- what use some sort of css...overflow? and scroll down..
- Server...some sort of http...how would the request wwork? number of posts or tweets etc..
- View would just contain the scroll component....and...have data injected into the scroll component...and create child components for posts and tweets...
  ...each subcomponent would render on the type of data that's being received
- not much commputation occur...but maybe if there's functionality of buttons
  - Commentts - server / post request
  - retweets
  - likes - server / post
  - boomarks - this might be have to live in local storage

View UI

- contains Scroll Component /Feed
- Post composer inside of

Data Model

```

const feed = {
    pagination_metadata: {

    }

    posts: Post[]

}

consts posts = {
    posts: [
        {
            creator: User,
            createdAt: Date
            comment: string,
            replies: []Reply,
            respostNum: number,
            likesNum: number,
            viewsNum: number
            metaData
        }
        ...
    ]
}

```

# Interface Definition

- API
- GET /feed ...returning the feed object with pagination
- Post /feed ...any persisted data update

GET feed parameters

```
    "size": 10,
    "cursor": looks like some hash... "=dXNlcjpXMDdRQ1JQQTQ"
```

Response

```
{
    "pagination": {
        "size": 10,
        "author": {
            "id": 123,
            "name" John Doe
        }
        "content": "lorem ipsum",
        "image": "https://bucket-hosting/some-image.jpg",
        "reactions": {
            "likes": 20,
            "dislikes" 10,
        }
        "create_time": 1620112
    }
}

```

## Optimizations and Deep Dive

- What if a user continually scrolls down or keeps pagination going...we don't want to keep hitting..
  so use some sort of `debounce` or `throttle`...
- time to first byte....since most users just get the first 10 posts... can we optimize that... TTFB
- what should the loading experience be.... skeleton or just a plain loading icon
- do we need to add any keyboard ineeractions?
- visual issues?
- a11y (acessability) for each of the component
- does the component have different experience with scroll... mobile vs desktop..Feed should still exist but sidebars concerning account details can be used in settings button...side bar with buttons can be used for other types of pages as well...
- Post tweet should be at top...with feed of posts at the bottom ...with pagination

# After Review

# Requirements

- User and friends
- Liking and reacting to feed posts
- Creating and publishing new posts
- commenting and sharing... extra
- what kind of posts are supported?
  - primarily texts and images
- What kind of pagination ux for feed?
  - infinite scrolling
- applicaition used on mobile device?

# Architecture

- Component Responibilities

  - Server
  - Controller
  - Client Store
  - Feed UI
    - Feed Posts
    - Post Composter (what you see is what you get WSYIWGY) editors for users to create new feed posts

- Rendering Approach
  - client side rendering (CSR)
  - server side rendering (SSR)
  - difference on where html is rendered
  - hybrid approach.. initial load with SSR ...to get a faster time to first byte... then CSR on user interactions...
  - need to dive in https://nextjs.org/

## Data model

- Feed
  - server
  - feed ui
  - posts .. list of Post, and pagination
- Post
  - server
  - Feed post
  - id, created_time, content, author (User), reactions, image_url
- User
  - server
  - client store
  - id, name, profile_photo_url
- NewPost
  - userinput
  - Post composer Ui
  - message, image

Advanced Normalized Store

- GraphQL can normalize data ...making it cleaner to for the frontend..more useful with various datasources. Reduce duplicate data and update data to same entity

## Interface Definition (API)

- Controller ..fetch feed posts
- Feedui gets data from ctontroller
- Feedui posts dat to controller
- post composter transfers post data to controller

using `GET` with `/feed`

- paginiation
  - offset-based pagination
  - cursor-based pagination

offset-based pagination

- parameters: size and page

```
{
    "pagination": {
        "size": 5,
        "page": 2,
        "total_pages": 4,
        "total": 20
    }
      "results": [
    {
      "id": "123",
      "author": {
        "id": "456",
        "name": "John Doe"
      },
      "content": "Hello world",
      "image": "https://www.example.com/feed-images.jpg",
      "reactions": {
        "likes": 20,
        "haha": 15
      },
      "created_time": 1620639583
    }
    // ... More posts.
  ]
}
```

underlying SQL

```
SELECT * FROM posts LIMIT 5 OFFSET 0; -- First page
SELECT * FROM posts LIMIT 5 OFFSET 5; -- Second page
```

backend implementation

```
(page - 1) * size.
```

inaccurate page results because new posts keeps coming in..

query performance degrades as the offset gets larger

Cursor-based-pagination

- parameters, `size` and `cursor`
- gets X numbers of posts of last cursor post

```
{
  "pagination": {
    "size": 10,
    "next_cursor": "=dXNlcjpVMEc5V0ZYTlo"
  },
  "results": [
    {
      "id": "123",
      "author": {
        "id": "456",
        "name": "John Doe"
      },
      "content": "Hello world",
      "image": "https://www.example.com/feed-images.jpg",
      "reactions": {
        "likes": 20,
        "haha": 15
      },
      "created_time": 1620639583
    }
    // ... More posts.
  ]
}

```

Advantages

- efficient for larger datasets
- more accurate posts
- uniquely map the cursor to a row...by using db's tables primary key ..or timestamp...

cursor better for infinite scroll (social media)..offset better for static list views... like list of transactions (banks)

# Optimizations and Deep Dives

Code splitting javascript

- split on page level
- lazy loading resources within a page

needs lazy loading for infinite scroll

Javascript loading
3 tiers

- (1) basic layout to display the first pain above the fold content (skeletons)
- (2) rendering content above the fold
- (3) resources that load that doesn't need FCP

Keyboard shortcuts

- shift ? ...for shortcuts

Error States

- error states ....network request failed or error netowrk connectivity

Feed list
infinite scrolling
....scroll down... then see loading indicator..
viewport height should be the trigger

Two ways to implement

- 1. listen for scroll event... with `setInterval`..and check position for marker element....by doing
     `Element.getBoundingClientRect`

- 2. Intersection Observer Api ... monitors for marking element or by specific amount

Virtualized Lists

- only render doms in the viewport ..as having too much will pollute the dom..(more memory)
- browser painting (less nodes to paint)
- VDOM reconillation ... less nodes then smaller diff to check .. better performance

Loading indicators:

- shimmer loading effect rather than loading indicator

Dynamic loading content:

- don't know the view port..so have to "guess"...subsequent request, viewport is known and able to calculate

Stalte feeds

- prompt user to refresh or ..automatically force refresh and scroll to the top

Feed post optimizations

Delivering data=drive dependencies only when needed

- Lazy load can can be expensive...

Facebook + relay couples components with data fields
like so...

```
// Sample GraphQL query to demonstrate data-driven dependencies.
... on Post {
  ... on TextPost {
    @module('TextComponent.js')
    contents
  }
  ... on ImagePost {
    @module('ImageComponent.js')
    image_data {
      alt
      dimensions
    }
  }
}
```

Rendering mentions and hashtags

- not all content is text..some is html..like hashtags..and emojis ..they have links

Html could be used but could risky with cross-site-scripting XSS
custom syntax

- hashtag can be found with #
- mentions

popular rich text edidtor like facebook's lexical...creates an AST like so

```
{
  content: [
    {
      type: 'HASHTAG',
      content: '#AboutLastNight',
    },
    {
      type: 'TEXT',
      content: ' is here... and ready to change ... Dropping 2/10 on ',
    },
    {
      type: 'MENTION',
      content: 'HBO Max',
      entityID: 1234,
    },
    {
      type: 'TEXT',
      content: '!',
    },
  ];
}
```

Rendering Images

- CDN
- modern image formats like webP
- <img> should have alot
- srcset for different viewport sizes
- adaptive loading on networking speed
  - devices with good internet can prefetch images
  - poor internet connection - low resolution images

Lazy Load code that is not needed for initial render

- reactions popover
- dropdown menu when to conceal additional actions
- components can load when browser is idle or demand when mouse hover over (tier 3)

Optimistic updates

- change the ui as if the server makes a complete request...otherwise revert ui changes and display error message
  ...immediately showing showers reaction and updated total count for reactions... relay,swr, react-query uses this

Timestamp rendering

- useful for multilingual timestamps and stale relative timestamps

few ways to support

- (1) server returns raw timestamp and client can parse in whatever language
- (2) - server returns timestamp in translated timestamp
- (3) javascript using ... `Intl.DateTimeFormat` API

stale timestamps ...can be refreshed

Icon Rendering

- usually svg is the way to go... scalable and crisb... has a flicker when downloading..but maybe a skeleton is good?.. what other optimizations

Post truncation

- John, Mary and 103k others ...
- shouldn't send the whole list of users...too much data!

Feed comments

- cursor based pagination for list of comments
- draft/editing ..simiar to posts
- lazy load emoji sticker pickers
- optimistic updates
  - immediately reflect new comments
  - display new reactions and update reaction counts

Live comment updates

- short polling
- long polling
- Server-sent events SSE
- Websockets
- HTTP/2 server push

Facebook uses websockets ... have to be careful to only show posts via more popular users

Feed composter optimizations

- WSSIWYG editing experience

- `contenteditable` for `textarea` or `input`
- open sources RTE frameworks

Lazy load dependencies

- image uploader
- gif picker
- emoji picker
- sticker picker
- background images

Acessaibility

- Feedlist ... `role=feed`
- Feed posts `role="article`, `aria-lablledby=<id>`
- fousable via keyboards with `tabindex="0` and appropriate `aria-role`

Feed interactions

- more feed reactions by hovering over lick button
- icon-buttons should have aria-label if there are no accompanying labels
