All API use should take place over SSL. All API usage should include a consumer key as a query parameter named 'key'. Consumer keys may be obtained from Futures.

Unauthenticated APIs:
GET /api/v1/assessment
GET /api/v1/careers/search
GET /api/v1/careers/:soc_code
GET /api/v1/careers/:riasec/:skills
GET /api/v1/industries
GET /api/v1/industries/:id
GET /api/v1/jobs/search
GET /api/v1/jobs/:id
POST /api/v1/user

Authentication is achieved with basic auth using the user's email and password. 

Authenticated APIs:
POST /api/v1/jobs/:id/apply

GET /api/v1/portfolio
POST /api/v1/portfolio
PUT /api/v1/portfolio
POST /api/v1/portfolio/military_histories
PUT /api/v1/portfolio/military_histories/:id
DELETE /api/v1/portfolio/military_histories/:id
POST /api/v1/portfolio/civilian_histories
PUT /api/v1/portfolio/civilian_histories/:id
DELETE /api/v1/portfolio/civilian_histories/:id

GET /api/v1/user
PUT /api/v1/user
