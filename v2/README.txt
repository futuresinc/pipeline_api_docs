All API use should take place over SSL. All API usage should include a consumer key as a query parameter named 'key'. Consumer keys may be obtained from Futures.

Unauthenticated APIs:
GET /api/v2/assessment.json
GET /api/v2/careers/search.json
GET /api/v2/careers/:soc_code.json
GET /api/v2/careers/:riasec/:skills.json
GET /api/v2/industries.json
GET /api/v2/industries/:id.json
GET /api/v2/jobs/search.json
GET /api/v2/jobs/:id.json
POST /api/v2/user.json

Authentication is achieved with basic auth using the user's email and password. 

Authenticated APIs:
POST /api/v2/jobs/:id/apply.json

GET /api/v2/portfolio.json
POST /api/v2/portfolio.json
PUT /api/v2/portfolio.json
POST /api/v2/portfolio/military_histories.json
PUT /api/v2/portfolio/military_histories/:id.json
DELETE /api/v2/portfolio/military_histories/:id.json
POST /api/v2/portfolio/civilian_histories.json
PUT /api/v2/portfolio/civilian_histories/:id.json
DELETE /api/v2/portfolio/civilian_histories/:id.json

GET /api/v2/user.json
PUT /api/v2/user.json


V2 Notes:

* Changes to valid values for portfolio military_status field.
* Possible inclusion of results from Job Aggregators (Indeed)
