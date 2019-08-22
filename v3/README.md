All API use should take place over SSL. All API usage should include a consumer
key as a query parameter named 'key'. Consumer keys may be obtained from
Futures.

Unauthenticated APIs:
* `GET /api/v3/careers/search`
* `GET /api/v3/careers/:soc_code`
* `GET /api/v3/industries`
* `GET /api/v3/industries/:id`
* `GET /api/v3/jobs/search`
* `GET /api/v3/jobs/:id`
* `POST /api/v3/user`

Authentication is achieved with basic auth using the user's email and password.

Authenticated APIs:
* `POST /api/v3/jobs/:id/apply`

* `GET /api/v3/portfolio`
* `POST /api/v3/portfolio`
* `PUT /api/v3/portfolio`
* `POST /api/v3/portfolio/military_histories`
* `PUT /api/v3/portfolio/military_histories/:id`
* `DELETE /api/v3/portfolio/military_histories/:id`
* `POST /api/v3/portfolio/civilian_histories`
* `PUT /api/v3/portfolio/civilian_histories/:id`
* `DELETE /api/v3/portfolio/civilian_histories/:id`

* `GET /api/v3/user`
* `PUT /api/v3/user`
