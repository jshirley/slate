# Errors

The TDP API uses the following error codes:


Error Code | Meaning
---------- | -------
400 | Bad Request -- Your request was not formed correctly
401 | Unauthorized -- Your API key is wrong
403 | Forbidden -- You do not have permission to the object requested
404 | Not Found -- Endpoint or object is not found
405 | Method Not Allowed -- The request method is not valid against that object
406 | Not Acceptable -- You requested a format that isn't supported (stick to JSON)
429 | Too Many Requests -- Temporary throttling, be reasonable with your API and you won't ever see this.
500 | Internal Server Error -- We had a problem with our server. Try again later.
503 | Service Unavailable -- We're temporarially offline (hopefully for maintanance). Please try again later.
