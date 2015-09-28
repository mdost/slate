# Errors

The ASP .NET library uses the following error codes:


Error Code | Meaning
---------- | -------
400 | Bad Request -- Incorrect Request
403 | Forbidden -- You cannot access this part
404 | Not Found -- Could not find your request
405 | Method Not Allowed -- You tried to access an entity with an invalid method
406 | Not Acceptable -- You requested a format that isn't json
500 | Internal Server Error -- We had a problem with our server. Try again later.
503 | Service Unavailable -- We're temporarially offline for maintanance. Please try again later.
