# Middleware functions 🌝

This document describes middleware functions build in our system.

Table of contents:

- [Middleware functions 🌝](#middleware-functions-%f0%9f%8c%9d)
  - [logger()](#logger)
  - [publicApi()](#publicapi)
  - [privateApi()](#privateapi)
  - [authorization()](#authorization)

## logger()

Created to log every api call to instance.

**Usage:**

```js
router.get("/some-route", logger(), (req, res) => {
  // handler
});
```

## publicApi()

Returns cors() middleware that allows all origins to access the route

**Usage:**

```js
router.get("/some-route", publicApi(), (req, res) => {
  // handler
});

// if used with authorization, place before
router.get("/some-route", publicApi(), authorization(), (req, res) => {
  // handler
});
```

## privateApi()

Returns cors() middleware that allows only selected origins

**Usage:**

```js
router.get("/some-route", privateApi(), (req, res) => {
  // handler
});

// if used with authorization, place before
router.get("/some-route", privateApi(), authorization(), (req, res) => {
  // handler
});
```

## authorization()

Validates token from `Authorization: Bearer <token>` format. If no token present, returns 401 HTTP error code.

After parsing token, validates ip source address with encapsulated into token and then checks either user role is allowed to this api or not. If this step fails, returns 403 HTTP error code.

**Usage:**

```js
router.get("/some-route", authorization(), (req, res) => {
  // handler
});
```
