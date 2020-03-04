# Front-end reference

Table of contents:

- [Front-end reference](#front-end-reference)
  - [Components hierarchy](#components-hierarchy)
  - [Plugins](#plugins)
  - [Routes](#routes)
  - [Store](#store)
  - [Api](#api)
    - [validateToken(token)](#validatetokentoken)

## Components hierarchy

- [App (1 level router, root)](components/app.md)
  - [Auth](components/auth.md)
  - [Homepage](components/homepage.md)

## Plugins

- Dependencies
  - vue-cookies (16 KB unpacked) - working with cookies
- Dev dependencies
  - node-sass, sass-loader - Webpack loader for Sass

## Routes

- **"/"** - Lazy loading TheHomepage component. Aliases: **"/profile"**
- **"/auth"** - Lazy loading TheAuth component

## Store

## Api

### validateToken(token)

Calling api/token/validate (POST) method for validating local token.

Params:

- _token_ - String, local token
