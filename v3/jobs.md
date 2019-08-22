Note that the "url" and "apply_url" are urls into the web application. Using the API, they would be "https://<pipeline_domain>/api/v3/jobs/:id" and "https://<pipeline_domain>/api/v3/jobs/:id/apply" respectively.

Jobs returned can be locally available jobs from Pipeline or returned via web service from an aggregator, such as Indeed. A single response can return a mixture of results.

Field definitions:
id: This job's unique identifier.
title: The title of the job.
description: The description of the job.
city: The city where the job is located.
state: The state where the job is located.
company: Name of the company posting the job.
posted_on: The date the job was posted in yyyy-mm-dd format.
url: The URL of the individual web page for this job.
requires_ats_apply: Denotes whether an application to this job must occur outside of pipeline. If "true", then an application can only be performed by the user in a web browser at the "url" address.
has_details: Denotes whether the details for the job may be fetched. Attempts to fetch details for jobs where "has_details" is "false" will return 404.
apply_url: URL of the web page that the job may be applied at.
salary: Salary for this job. Rarely present.
salary_type: Type of salary. One of per_year or per_hour.
requisition_number: The requisition number as assigned by the company.

**SEARCH**

Job post json (search) (GET /api/v3/jobs/search?search[keywords]=computers&search[location]=NC&search[job_type]=full_time&search[distance]=25_miles):
[
 {
   "id": "1523-computer-security-incident-responder",
   "city": "Syracuse",
   "posted_on": "2011-10-07",
   "title": "Computer Security Incident Responder",
   "company": "JPMorgan Chase",
   "description": "The JPMorgan Chase Technology Center on the campus of Syracuse University is a firm-wide Center of Excellence for Information Security and Risk Management as well as a test bed for technology innovation.&amp;nbsp; The Tech center is a key component of our unique, industry leading partnership with Syracuse University.<br />\n<br />\n",
   "state": "NY",
   "url": "https://<pipeline_domain>/jobs/1523-computer-security-incident-responder"
   "requires_ats_apply": "true",
   "has_details": "true"
 }
]

Jobs from Indeed (aggregator) will instead have a 16 char alphanumeric id, and a url pointing to the post on the Indeed website:

{
  "id": "579bc5d7a3d30bf9",
  "title": "Junior Software Engineer",
  "city": "Baltimore",
  "state": "MD",
  "description": "Write software... ",
  "company": "Futures, Inc.",
  "posted_on": "2012-04-10",
  "url": "http://www.indeed.com/viewjob?jk=579bc5d7a3d30bf9&qd=d8ujaJN9ydMWUFT7aTpw0SGA9rpTdTNx9Kq5RIvEG6wbxO7H7iJ9xTE-Ft9RRtibvaauq8PNtjNMHK2vZJ-eoeoCFLMibOCEabUahnuewCk&indpubnum=294298244185573&rjs=1&atk=16tv089hj0k1113b",
  "requires_ats_apply": "true",
  "has_details": "false"
}

Valid parameters and values are:
search[keywords]: Free form text
search[location]: Free form text
search[job_type]: full_time, part_time
search[distance]: 25_miles, 50_miles, 75_miles, 100_miles
search[exact_title_phrase]: Free form text. Constrain the matches to include this exact and non-stemmed phrase in the title.
search[company_ids]: A comma delimited list of pipeline company ids. Constrains the matches to jobs associated to the one of the companies in the given list.
disable_aggregation: Set to '1' to disable the supplementing of pipeline jobs with ones from a search aggregator.

**DETAILS**

Additional job details can be fetched for jobs where "has_details" is set to "true". Attempts to fetch details for jobs with "has_details" set to "false" will result in a 404 response.

Job post json (details) (GET /api/v3/jobs/:id):
{
  "id": "1523-computer-security-incident-responder",
  "description": "The JPMorgan Chase Technology Center on the campus of Syracuse University is a firm-wide Center of Excellence for Information Security and Risk Management as well as a test bed for technology innovation.&amp;nbsp; The Tech center is a key component of our unique, industry leading partnership with Syracuse University.<br />\n<br />\n",
  "state": "NY",
  "job_type": "Full Time",
  "close_on": "2011-12-07",
  "posted_on": "2011-10-07",
  "apply_url": "https://<pipeline_domain>/job_inquiries?job_post_id=1523",
  "salary": "75000",
  "url": "https://<pipeline_domain>/jobs/1523-computer-security-incident-responder",
  "company": "JPMorgan Chase",
  "title": "Computer Security Incident Responder",
  "city": "Syracuse",
  "salary_type": "specified_amount",
  "requisition_number": "110060072"
}

**APPLY**

Job post apply is a POST with an empty body to /api/v3/jobs/1523-computer-security-incident-responder/apply. The status of the "apply" is returned.

A successful application to a pipeline job:
{
  "status": "success"
}

An attempt to apply to a job that requires the application to take place in an ats system:
{
  "status": "requires_ats_apply",
  "ats_url": "https://jobs.example.com/job/11212434342"
}

Attempting to apply to a job twice will return a 422 with the following error:
{
  "status": "failed",
  "errors": "You have already applied for this job and the employer currently has access to your Portfolio."
}
