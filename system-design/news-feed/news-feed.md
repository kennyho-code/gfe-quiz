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
