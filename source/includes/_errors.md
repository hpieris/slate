# Errors


Error Code | Meaning
---------- | -------
400 | Bad Request -- Your request sucks
401 | Unauthorized -- Your API key is wrong
403 | Forbidden -- The requested object is hidden for administrators only
404 | Not Found -- The specified object could not be found
405 | Method Not Allowed -- You tried to access a object with an invalid method
406 | Not Acceptable -- You requested a format that isn't json
410 | Gone -- The object requested has been removed from our servers
429 | Too Many Requests -- You're requesting too many objects! Slown down!
500 | Internal Server Error -- We had a problem with our server. Try again later.
503 | Service Unavailable -- We're temporarially offline for maintanance. Please try again later.