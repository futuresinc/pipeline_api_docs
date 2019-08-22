# `GET /api/v3/industries`

Returns array of parent industry object.

`id`: unique id, can be used to fetch individual industry details
`name`: name of industry

# `GET /api/v3/industries/:id`

Returns industry object, as above with additional fields:

`description`:  Long description of industry
`related_careers`: Array of objects
  `onet_soc_code`: O\*Net unique id for career
  `api_safe_onet_soc_code`: as above, but suitable for passing to careers api.
  `title`:  User friendly name of career
  `link`:  link to career detail page on pipeline website
  `average_national_salary`:  in dollars per year, if available
  `state_salaries`:  array of objects:
    `state`: 2 character state abbreviation
    `average_salary`: in dollars per year, if available
