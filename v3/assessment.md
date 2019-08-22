GET /api/v3/assessment

Returns an array of hashes:

text:  English text of question to ask user.
id:  unique name
answers:  hash with:
   text: English text of response choice to display to user.
   value:  programmatic value for submission to user.



GET /api/v3/careers/xxxxxx/yyyyyyyy

Example:  "/api/v3/careers/123453/12341234"

xxxxxx => results from the first 6 (interest) questions from above url
yyyyyyyy => results from last 8 (skills) questions from above url

Returns an array of career hashes.  See careers.txt


