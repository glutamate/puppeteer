---
sidebar_label: HTTPRequest
---

# HTTPRequest class

Represents an HTTP request sent by a page.

#### Signature:

```typescript
export declare class HTTPRequest
```

## Remarks

Whenever the page sends a request, such as for a network resource, the following events are emitted by Puppeteer's `page`:

- `request`: emitted when the request is issued by the page. - `requestfinished` - emitted when the response body is downloaded and the request is complete.

If request fails at some point, then instead of `requestfinished` event the `requestfailed` event is emitted.

All of these events provide an instance of `HTTPRequest` representing the request that occurred:

```
page.on('request', request => ...)
```

NOTE: HTTP Error responses, such as 404 or 503, are still successful responses from HTTP standpoint, so request will complete with `requestfinished` event.

If request gets a 'redirect' response, the request is successfully finished with the `requestfinished` event, and a new request is issued to a redirected url.

The constructor for this class is marked as internal. Third-party code should not call the constructor directly or create subclasses that extend the `HTTPRequest` class.

## Properties

| Property | Modifiers             | Type                                    | Description                                                       |
| -------- | --------------------- | --------------------------------------- | ----------------------------------------------------------------- |
| client   | <code>readonly</code> | [CDPSession](./puppeteer.cdpsession.md) | Warning! Using this client can break Puppeteer. Use with caution. |

## Methods

| Method                                                                                      | Modifiers | Description                                                                                                                                                                                                      |
| ------------------------------------------------------------------------------------------- | --------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [abort(errorCode, priority)](./puppeteer.httprequest.abort.md)                              |           | Aborts a request.                                                                                                                                                                                                |
| [abortErrorReason()](./puppeteer.httprequest.aborterrorreason.md)                           |           |                                                                                                                                                                                                                  |
| [continue(overrides, priority)](./puppeteer.httprequest.continue.md)                        |           | Continues request with optional request overrides.                                                                                                                                                               |
| [continueRequestOverrides()](./puppeteer.httprequest.continuerequestoverrides.md)           |           |                                                                                                                                                                                                                  |
| [enqueueInterceptAction(pendingHandler)](./puppeteer.httprequest.enqueueinterceptaction.md) |           | Adds an async request handler to the processing queue. Deferred handlers are not guaranteed to execute in any particular order, but they are guaranteed to resolve before the request interception is finalized. |
| [failure()](./puppeteer.httprequest.failure.md)                                             |           | Access information about the request's failure.                                                                                                                                                                  |
| [finalizeInterceptions()](./puppeteer.httprequest.finalizeinterceptions.md)                 |           | Awaits pending interception handlers and then decides how to fulfill the request interception.                                                                                                                   |
| [frame()](./puppeteer.httprequest.frame.md)                                                 |           |                                                                                                                                                                                                                  |
| [headers()](./puppeteer.httprequest.headers.md)                                             |           |                                                                                                                                                                                                                  |
| [initiator()](./puppeteer.httprequest.initiator.md)                                         |           |                                                                                                                                                                                                                  |
| [interceptResolutionState()](./puppeteer.httprequest.interceptresolutionstate.md)           |           |                                                                                                                                                                                                                  |
| [isInterceptResolutionHandled()](./puppeteer.httprequest.isinterceptresolutionhandled.md)   |           |                                                                                                                                                                                                                  |
| [isNavigationRequest()](./puppeteer.httprequest.isnavigationrequest.md)                     |           |                                                                                                                                                                                                                  |
| [method()](./puppeteer.httprequest.method.md)                                               |           |                                                                                                                                                                                                                  |
| [postData()](./puppeteer.httprequest.postdata.md)                                           |           |                                                                                                                                                                                                                  |
| [redirectChain()](./puppeteer.httprequest.redirectchain.md)                                 |           | A <code>redirectChain</code> is a chain of requests initiated to fetch a resource.                                                                                                                               |
| [resourceType()](./puppeteer.httprequest.resourcetype.md)                                   |           | Contains the request's resource type as it was perceived by the rendering engine.                                                                                                                                |
| [respond(response, priority)](./puppeteer.httprequest.respond.md)                           |           | Fulfills a request with the given response.                                                                                                                                                                      |
| [response()](./puppeteer.httprequest.response.md)                                           |           |                                                                                                                                                                                                                  |
| [responseForRequest()](./puppeteer.httprequest.responseforrequest.md)                       |           |                                                                                                                                                                                                                  |
| [url()](./puppeteer.httprequest.url.md)                                                     |           |                                                                                                                                                                                                                  |
