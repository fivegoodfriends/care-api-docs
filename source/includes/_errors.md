# Errors

The most likely error codes from the Lookout App API are listed below, others in the >400 range may also be returned:


Error Code | Meaning
---------- | -------
400 | Bad Request -- Your request is invalid.
401 | Unauthorized -- Your API key is wrong.
403 | Forbidden -- Your API Key was correct, but you cannot access this thing.
404 | Not Found -- The specified thing could not be found.
406 | Not Acceptable -- You requested a format that isn't json.
422 | Unprocessable entity -- Something went wrong in your request, did you miss a header?
429 | Too Many Requests -- You're requesting too many things! Slow down!
500 | Internal Server Error -- We had a problem with our server. Try again later.
503 | Service Unavailable -- We're temporarily offline for maintenance. Please try again later.
