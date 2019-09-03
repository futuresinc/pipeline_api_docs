# `GET /api/v3/industries`

Returns array of parent industry object.

`id`: unique id, can be used to fetch individual industry details
`name`: name of industry
`link`: link to the industry detail page on the pipeline website
`image_url`: URL of the main image used on the industry page

# `GET /api/v3/industries/:id`

Returns industry object, as above with additional fields:

* `id`: unique id, can be used to fetch individual industry details
* `name`: name of industry
* `link`: link to the industry detail page on the pipeline website
* `image_url`: URL of the main image used on the industry page
* `description`:  Long description of industry
* `news`: Aggregated news posts for this industry. Array of objects in the format:
- `title`: Article title
- `snippet`: Brief exerpt from the article
- `image_url`: URL of the main image for the article (optional)
- `link`: Link to the article
* `related_careers`: Careers related to this industry. Array of objects in the same format as the [Careers Details Endpoint](careers.md)
* `top_careers`: Top/Hot related careers. Array of objects in the same format as the [Careers Details Endpoint](careers.md)
