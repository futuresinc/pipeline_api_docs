# `GET /api/v3/careers`

## Params

`page`: First request returns 10 results (page 1). Incrementing returns the next 10.

## Returns

Array of objects representing a Career

* `onet_soc_code`: O\*Net unique id for career
* `api_safe_onet_soc_code`: as above, but suitable for passing to careers api.
* `title`:  User friendly name of career
* `link`:  link to career detail page on pipeline website
* `image_url`:  url of the main image used for the career
* `image_medium_url`:  url of the main image used for the career in a medium sizing
* `education_level`: Level of education required for this career. One of `less_than_a_high_school_diploma`, `high_school_diploma`, `post_secondary_certificate`, `some_college_courses`, `associates_degree`, `bachelors_degree`, `post_baccalaureate_certificate`, `masters_degree`, `post_masters_certificate`, `first_professional_degree`, `doctoral_degree`, `post_doctoral_training`.
* `average_national_salary`:  in dollars per year, if available
* `state_salaries`:  array of objects:
*   `state`: 2 character state abbreviation
*   `average_salary`: in dollars per year, if available

# `GET /api/v3/careers/search?q=:keywords`

Returns array of objects as per above.

# `GET /api/v3/careers/:api_safe_onet_soc_code>`

Returns a single career object.  As above, with extra fields:

* `onet_soc_code`: O\*Net unique id for career
* `api_safe_onet_soc_code`: as above, but suitable for passing to careers api.
* `title`:  User friendly name of career
* `link`:  link to career detail page on pipeline website
* `image_url`:  url of the main image used for the career
* `image_medium_url`:  url of the main image used for the career in a medium sizing
* `education_level`: Level of education required for this career. One of `less_than_a_high_school_diploma`, `high_school_diploma`, `post_secondary_certificate`, `some_college_courses`, `associates_degree`, `bachelors_degree`, `post_baccalaureate_certificate`, `masters_degree`, `post_masters_certificate`, `first_professional_degree`, `doctoral_degree`, `post_doctoral_training`.
* `average_national_salary`:  in dollars per year, if available
* `description`:  Long text description of career.
* `entry_job_title`: Title of the entry-level job for this career
* `mid_job_title`: Title of the mid-level job for this career
* `advanced_job_title`: Title of the advanced-level job for this career
* `associated_jobs_link`:  Link to pipeline website search for related jobs.
* `related_careers`: Objects of other careers related to this one.
-   `onet_soc_code`: O\*Net unique id for career
-   `api_safe_onet_soc_code`: as above, but suitable for passing to careers api.
-   `title`:  User friendly name of career
* `certifications`: Certifications associated with this career. Array of objects:
-   `name`: Name of the certification
-   `type`: One of `Core`, `Advanced`, or `Specialty`
-   `link`: URL of the certification on the provider's site
* `state_salaries`:  array of objects:
-   `state`: 2 character state abbreviation
-   `low_salary`: in dollars per year, if available
-   `average_salary`: in dollars per year, if available
-   `high_salary`: in dollars per year, if available
-   `low_hourly`: in dollars per year, if available
-   `average_hourly`: in dollars per year, if available
-   `high_hourly`: in dollars per year, if available
* `knowledge`: types of knowledge required.  array of objects:
-   `title`:  Short description of knowledge
-   `description`:  Long description
* `skills`:  skills required for career.  array of objects:
-   `title`:  Short description of skill.
* `abilities`:  abilities required.  array of objets:
-   `title`:  Short description of ability
-   `description`:  Long description
* `significant_points`:  array of facts about current state of career
* `simple_tasks`:  array of descriptions of tasks associated with career
* `work_styles`: attributes associated with the career.  array of hashes:
-   `title`:  short description of style
-   `description`:  long description
* `programs`: Educational programs associated with this career. Array of objects:
-   `name`: Name of the program
-   `educator_name`: Name of the educator offering this program
-   `type`: Type of program offered. One of `associates_degree`, `bachelors_degree`, or `other`
-   `link`: URL of the program's details on the educator's site
