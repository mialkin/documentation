# Idempotency

**Idempotency** is the property that an operation may be applied multiple times with the result not differing from the first application. Restated, that means multiple identical requests should have the same effect as a single request.

## Idempotent Requests

An idempotent API allows safely retry requests without accidentally performing the same operation twice. This is useful when an API call is disrupted in transit and you do not receive a response. For example, if a request to create a payment does not respond due to a network connection error, you can retry the request with the same idempotency key to guarantee that no more than one charge is created.

An idempotency key is a unique value generated by the client which the server uses to recognize subsequent retries of the same request. How you create unique keys is up to you (for example V4 UUIDs), but make sure that the resulting random string has enough entropy to avoid collisions.

All `POST` requests accept idempotency keys. Sending idempotency keys in `GET` and `DELETE` requests has no effect and should be avoided, as these requests are idempotent by definition.