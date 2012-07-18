All API use should take place over SSL. All API usage should include a consumer key as a query parameter named 'key'. Consumer keys may be obtained from Futures.

Unauthenticated APIs:
GET /api/v2/assessment
GET /api/v2/careers/search
GET /api/v2/careers/:soc_code
GET /api/v2/careers/:riasec/:skills
GET /api/v2/industries
GET /api/v2/industries/:id
GET /api/v2/jobs/search
GET /api/v2/jobs/:id
POST /api/v2/user

Authentication is achieved with basic auth using the user's email and password. 

Authenticated APIs:
POST /api/v2/jobs/:id/apply

GET /api/v2/portfolio
POST /api/v2/portfolio
PUT /api/v2/portfolio
POST /api/v2/portfolio/military_histories
PUT /api/v2/portfolio/military_histories/:id
DELETE /api/v2/portfolio/military_histories/:id
POST /api/v2/portfolio/civilian_histories
PUT /api/v2/portfolio/civilian_histories/:id
DELETE /api/v2/portfolio/civilian_histories/:id

GET /api/v2/user
PUT /api/v2/user


V2 Notes:

* Changes to valid values for portfolio military_status field.
* Inclusion of results from Job Aggregators (Indeed). A GET to fetch additional details for an aggregated job ("has_details" set to "false") is not supported.
