GET /api/v3/careers

Params:

  page:  first request returns 10 results (page 1).  Incrementing page
  returns the next 10.


Returns:

Array of hashes representing an O*Net Occupation (Career)

onet_soc_code: O*Net unique id for career
api_safe_onet_soc_code: as above, but suitable for passing to careers api.
title:  User friendly name of career
link:  link to career detail page on pipeline website
average_national_salary:  in dollars per year, if available
state_salaries:  array of hashes:
  state: 2 character state abbreviation
  average_salary: in dollars per year, if available


GET /api/v3/careers/search?q=<keywords>

Returns array of hashes as per above.


GET /api/v3/careers/<api_safe_onet_soc_code>

Returns a single career hash.  As above, with extra fields:

description:  Long text description of career.
associated_jobs_link:  Link to pipeline website search for related jobs.
related_careers:
knowledge: types of knowledge required.  array of hashes:
  title:  Short description of knowledge
  description:  Long description
  stars:  integer 1-5, relevance of knowledge to career
skills:  skills required for career.  array of hashes:
  title:  Short description of skill.
  stars:  integer 1-5, relevance of skill to career
abilities:  abilities required.  array of hashes:
  title:  Short description of ability
  description:  Long description
  stars:  integer 1-5, relevance of ability to career
additional_training_experience:  experience/training required. array of hashes:
  name: Type of experience
  description: details of experience
significant_points:  array of facts about current state of career
video: Link to pipeline video for career
simple_tasks:  array of descriptions of tasks associated with career
work_styles: attributes associated with the career.  array of hashes:
  title:  short description of style
  description:  long description
