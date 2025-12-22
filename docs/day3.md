## CORS (Cross-Origin Resource Sharing)
CORS is a browser security mechanism that restricts requests
from one origin to another unless explicitly allowed by the server.

When frontend and backend run on different origins,
the backend must send appropriate CORS headers.

In Express, CORS can be enabled using the `cors` middleware.


## Day 3 Summary
- Created POST APIs using Express
- Used express.json() to parse request bodies
- Sent data from frontend using fetch()
- Understood CORS and preflight OPTIONS requests
- Fixed origin mismatch issues
- Resolved EADDRINUSE port conflict


## If interviewer asks:

-“How does frontend send data to backend?”

-You can answer:

-“Using POST requests with JSON body, parsed by express.json(). Cross-origin requests are handled -using CORS middleware, and browsers send preflight OPTIONS requests before POST.”
