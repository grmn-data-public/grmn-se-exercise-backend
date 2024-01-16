# Counter Service

You are to create a webservice that keeps track of counters. It should have the following
capabilities:
1. Creating a counter
2. Incrementing a counter by 1
3. Reading a counter

For example, the API spec for such a service could look like this:

1. `POST /counter`, the response of which should contain the =id= of the counter.
2. `PATCH /counter/{:id}`
3. `GET /counter/{:id}`

A specific sequence of requests like:

1. `POST /counter`, creating a counter with id 1
2. `PATCH /counter/1`
3. `PATCH /counter/1`

should result in a state in which the following `GET /counter/1` request should return a value
of 2. There are no other implementation requirements; for example, you are free to use a database to
store the counters.



