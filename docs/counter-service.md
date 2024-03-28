# Counter Service

## Functional requirements

You are to create a webservice that keeps track of counters. It should have the following
capabilities:
1. Creating a counter, in which the initial value of the counter should be part of the request.
2. Incrementing a counter by 1
3. Reading a counter

For example, the API spec for such a service could look like this:

1. `POST /counter`, the response of which should contain the `id` of the counter.
2. `PATCH /counter/{:id}`
3. `GET /counter/{:id}`

A specific sequence of requests like:

1. `POST /counter`, creating a counter with id 1
2. `PATCH /counter/1`
3. `PATCH /counter/1`

should result in a state in which the following `GET /counter/1` request should return a value
of 2. Note that the service should still perform correctly under concurrent requests, e.g., two
concurrent `PATCH` requests to the same counter should result in the counter being increased by two.

## Non-functional requirements

* The documentation should have instructions for running the service, e.g., it should be easy for us
  to get a functional counter service up an running.
* The code should be stored in a Git repo.

## Hints

* You are free to choose how to store the counters, using an in-memory data structure, or an
  external database are both valid options.
* Focus on creating clean and modular code.
* Implement proper validation and error handling.

## Suggestions

### Python

* A simple framework to use for setting up a webservice is [Flask](https://pypi.org/project/Flask/),
  or if you like Python type hinting and async functions,
  [FastAPI](https://pypi.org/project/fastapi/).
