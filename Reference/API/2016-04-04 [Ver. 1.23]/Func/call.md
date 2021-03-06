# Call a function

```
GET/POST/PUT/DELETE https://$region.hyperfunc.io/call/$name/$uuid[/sync]

{payload}
```

Call a function (by default the call is asynchronous, add the `/sync` parameter for synchronous call).

**The endpoint should be `$region.hyperfunc.io`, and no signature authentication requirements.**

**Example call**:

```
POST https://us-west-1.hyperfunc.io/call/helloworld/e62c014e-386c-42ea-8d07-41d44e98cc3d HTTP/1.1

Hello
```

**Example response**:

```
HTTP/1.1 200 OK
Content-Type: application/json

{
  "CallId": "218b7b10-e7f1-4c48-ac3c-66792f8ffc06"
}
```

**URL parameters**:

* $region - Supported region.
* $name - The function name.
* $uuid - The uuid of func.
* /sync - Block until the function call has completed.

**Json parameters**:

* CallId - The call id of a function call.

**Status Codes**:

* 200 - no error
* 404 - no such function
* 413 - request entity too large
* 500 - server error
* If the `/sync` parameter is used: same status codes as with the [get](./get.md) endpoint.

**Notes**

* The finished/failed function call will be removed once the api with `/sync` parameter is successfully called.
