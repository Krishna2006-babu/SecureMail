## CORS (Cross-Origin Resource Sharing)
CORS is a browser security mechanism that restricts requests
from one origin to another unless explicitly allowed by the server.

When frontend and backend run on different origins,
the backend must send appropriate CORS headers.

In Express, CORS can be enabled using the `cors` middleware.
