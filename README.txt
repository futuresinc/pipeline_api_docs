All API use should take place over SSL. All API usage should include a consumer key as a query parameter named 'key'. Consumer keys may be obtained from Futures.

Unauthenticated APIs:
GET /api/v1/assessment.json
GET /api/v1/careers/search.json
GET /api/v1/careers/:soc_code.json
GET /api/v1/careers/:riasec/:skills.json
GET /api/v1/industries.json
GET /api/v1/industries/:id.json
GET /api/v1/jobs/search.json
GET /api/v1/jobs/:id.json

Authentication is achieved with basic auth using the user's email and password. 

Authenticated APIs:
POST /api/v1/jobs/:id/apply.json
GET /api/v1/portfolio.json
POST /api/v1/portfolio.json
PUT /api/v1/portfolio.json