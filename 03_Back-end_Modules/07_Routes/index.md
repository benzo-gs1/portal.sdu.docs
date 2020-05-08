# Routes

This document describes how to define your own controllers and build api with it.

## Tools

There are plenty defined decorators, interfaces and types to work with:

```ts
/*
  Controller is used to
  declare Route controller class with given prefix
*/
export function Controller(prefix: string);

/*
  Public is used to define public api,
  this will set publicApi middleware to route
*/
export function Public(target: any, key: string, descriptor: PropertyDescriptor);

/*
  Private is used to define private api,
  this will set privateApi middleware to route
*/
export function Private(target: any, key: string, descriptor: PropertyDescriptor);

/*
  Protected us used to define protected route (by token),
  this will set authorization middleware to route
*/
export function Protected(target: any, key: string, descriptor: PropertyDescriptor);

/*
  Test is used to define test route.
  Such routes won't be collected in production mode
*/
export function Test(target: any, key: string, descriptor: PropertyDescriptor);

/*
  Route definitions are used 
  to define api end points
*/
export function Get(path: string);
export function Post(path: string);
export function Put(path: string);
export function Delete(path: string);

// Used by RouteResponse
type ResponseData = Object | Array<any>;

/*
  Route response class must be used 
  to respond from api end point method
*/
class RouteResponse {
  /*
    You could create RouteResponse object
    and then return it
  */
  constructor(message: string, code = 200, status = true, data = {});

  /*
    Create RouteResponse object with status true
  */
  public static say(message: string, code = 200, status = true): RouteResponse;

  /*
    Create RouteResponse object with status false
  */
  public static deny(message: string, code = 400, status = false): RouteResponse;

  /*
    Set message to the instance
  */
  public say(message: string): this;

  /*
    Set response data to the instance
  */
  public send(data: ResponseData): this;

  /*
    Set response http status code to the instance
  */
  public http(code: number): this;

  /*
    Set response status to the instance
  */
  public stat(status: boolean);
}

// Used in route-collector
export interface RouteDefinition {
  // Path to our route
  path: string;
  // HTTP Request method (get, post, ...)
  requestMethod: method;
  // Method name within our class responsible for this route
  methodName: string;
}
```

## Example

### Creating Controller

```ts
// routes/example/index.ts

import { Controller } from "@/utils";

// prefix api/example
@Controller("/example")
class ExampleController {
  // end points
}

export default ExampleController;
```

### Creating api end point

```ts
// routes/example/index.ts

import { Controller, Get, Public } from "@/utils";

// prefix api/example
@Controller("/example")
class ExampleController {
  // public api end point at api/example/fetch
  @Public
  @Get("/fetch")
  public fetch() {
    // code
  }
}

export default ExampleController;
```

### Creating protected, test api

```ts
// routes/example/index.ts

import { Controller, Get, Public, Test, Protected } from "@/utils";

// prefix api/example
@Controller("/example")
class ExampleController {
  // public, test, protected api end point at api/example/fetch, order of decorators does not matter
  @Test
  @Public
  @Protected
  @Get("/fetch")
  public fetch() {
    // code
  }
}

export default ExampleController;
```

### Response using static methods

```ts
// routes/example/index.ts

import { Controller, Get, RouteResponse, Public } from "@/utils";

// prefix api/example
@Controller("/example")
class ExampleController {
  // public api end point at api/example/fetch
  @Public
  @Get("/fetch")
  public fetch() {
    // Response with status true, code 200 and message Success (no data)
    return RouteResponse.say("Success");
  }
}

export default ExampleController;
```

### Response using class constructor

```ts
// routes/example/index.ts

import { Controller, Get, RouteResponse, Public } from "@/utils";

// prefix api/example
@Controller("/example")
class ExampleController {
  // public api end point at api/example/fetch
  @Public
  @Get("/fetch")
  public fetch() {
    // Response with status true, code 201 and message Success (no data)
    return new RouteResponse("Success").http(201);
  }
}

export default ExampleController;
```

### Chaining response methods

```ts
// routes/example/index.ts

import { Controller, Get, RouteResponse, Public } from "@/utils";

// prefix api/example
@Controller("/example")
class ExampleController {
  // public api end point at api/example/fetch
  @Public
  @Get("/fetch")
  public fetch() {
    // Response with status true, code 201 and message Success (no data)
    return RouteResponse.say("Success")
      .http(201)
      .status(true) // true is already set by default
      .send(
        // object or array
        {} | []
      );
  }
}

export default ExampleController;
```
