# `GET /api/v3/careers`

## Params

`page`: First request returns 10 results (page 1). Incrementing returns the next 10.

## Returns

Array of objects representing a Career

`onet_soc_code`: O\*Net unique id for career
`api_safe_onet_soc_code`: as above, but suitable for passing to careers api.
`title`:  User friendly name of career
`link`:  link to career detail page on pipeline website
`average_national_salary`:  in dollars per year, if available
`state_salaries`:  array of objects:
  `state`: 2 character state abbreviation
  `average_salary`: in dollars per year, if available

# `GET /api/v3/careers/search?q=:keywords`

Returns array of objects as per above.

# `GET /api/v3/careers/:api_safe_onet_soc_code>`

Returns a single career object.  As above, with extra fields:

`description`:  Long text description of career.
`associated_jobs_link`:  Link to pipeline website search for related jobs.
`related_careers`: Objects of other careers related to this one.
`knowledge`: types of knowledge required.  array of objects:
  `title`:  Short description of knowledge
  `description`:  Long description
`skills`:  skills required for career.  array of objects:
  `title`:  Short description of skill.
`abilities`:  abilities required.  array of objets:
  `title`:  Short description of ability
  `description`:  Long description
`significant_points`:  array of facts about current state of career
`simple_tasks`:  array of descriptions of tasks associated with career
`work_styles`: attributes associated with the career.  array of hashes:
  `title`:  short description of style
  `description`:  long description
