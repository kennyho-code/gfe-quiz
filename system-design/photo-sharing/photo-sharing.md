# Photo Sharing

## Requirements

Functional Requirements

- we have to login
- we have to create a "user"
- you get "feed" of posts
  - pagination with infinite scrolling?
- people who you follow get priority
- your own posts

  - your own pictures...

- Non-functional
  - loading pictures
  - storing pictures

## Architecture

Feed Page

- Feed includes something news-feed
- Server
- Feed Ui
  - Posts
  - infinite scrolling pagination
  - cursor based
  - Post Composer

User Page

- server
- client store
- user
- posts
- new post

- Post Page

## Data Models

```
Post {
    id: uuid,
    create_time: datetime
    content: string
    author: user
    reactions: [likes, dislikes]
    image_url:
    comments: []Comment
}

Comment {
    author: user
    content: string
}

User {
    id
    name
    profile_photo_url
}

Feed {
    posts: []Post
    pagination: {
        size: number
        page: number
        total_pages: number
        total: number
    }
}
```

## Interfaces

... look into news feed

## Optimizations

... look into needsfeed for feed

- CDN for image formats
- Lazy Loading for components and content
- optimistic updates
- SVG icon rendering
- Post truncation
- Comments, press button for pagination
- Live Comment updates - websockets
- WSIWYG editing experience
- Accessibility - keyboard, role=feed, arialabey
- International

# Review

## Requirements

- examples: instagram, flikr
- similar: image caraousel, news feed

- browse feed image and video posts by people a user follows
- upload photos, apply captions, apply filters
- infinite scrolling
- onle overall caption per post
- primarily mobile...but should be usable on desktop and tablet

## Architectecture Diagram

- Server, Controller, Client Store, Feed UI (image post, post composter)

## Data Model

```
Feed{
    posts: []Post,
    pagination: {
        ...
    }
}

Post {
    id: uuid
    create_time: date
    caption: text
    image: url
    author: User
    images: []Image
}

User {
    id: uuid
    name: string
    photo_photo_url: url
}

NewPost {
    caption
    images: Image
}

Image {
    url: string
    alt: string
    width: number
    height: number
}

```

## Interface (API)

- Feed List api
- Post Creation API
  - (1) single api for uploading post creation and image uploading
  - (2) create separate APIs
    - this is better as they are decoupled for multiple features ...more flexible

## Optimizations

- News Feed
- Image caraousel
