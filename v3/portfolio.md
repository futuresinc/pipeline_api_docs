Portfolio json (GET /api/v3/portfolio):
{
  "first_name": "John",
  "last_name": "Dough",
  "military_status": "service_member",
  "estimated_separation_on": "2012-03-21",
  "rank": "first_lieutenant",
  "service": "army",
  "moc_code": "11B",
  "security_clearance": "active",
  "military_installation": "bragg",
  "resume_url": "http://uploads.pipeline/path/to/resume.txt",
  "resume_file_name": "resume.doc",
  "resume_file_size": 1430,
  "resume_content_type": "text/plain",
  "education_level": "post_secondary_certificate",
  "total_career_experience": "three_to_five_years",
  "career_level": "mid_level_manager",
  "minimum_salary": "50000_dollars",
  "summary": "I am a developer. You should hire me.",
  "keywords": "ruby java rails play",
  "street1": "123 Any St.",
  "street2": null,
  "city": "Raleigh",
  "state": "NC",
  "postal_code": "12345",
  "contact_number": "555-555-5555",
  "relocation": false,
  "resume_updated_at": "2011-11-29T17:38:32-05:00",
  "job_type": "full_time",
  "civilian_history": [
    {
      "id": 39393,
      "description": "Received customer food and drink orders, provided money handling service, cleaned establishment, and provided overall customer service.",
      "job_title": "Server",
      "started_on": "2011-03-01",
      "ended_on": "2011-06-01",
      "job_function": "hospitality",
      "company_name": "Cheers",
      "city": "Durham",
      "state": "NC",
    },
    {
      "id": 39399,
      "description": "Provided recruiting support to the US Army.",
      "job_title": "Marketing Specialist",
      "started_on": "2010-05-01",
      "ended_on": "2010-06-01",
      "job_function": "marketing",
      "company_name": "Marketing, Ltd.",
      "city": "Columbia",
      "state": "SC",
    }
  ],
  "military_history": [
    {
      "id": 40203,
      "description": "Trained and led junior soldiers in infantry tactics in both peace time and deployments.",
      "branch": "army",
      "started_on": "2004-03-01",
      "ended_on": "2005-05-01",
      "rank": "E-4",
      "moc": "11B2P",
      "service_field": "infantry",
      "city": "",
      "state": "",
    }
  ]
}

Valid keys and values (w/ descriptions):
first_name: Free form text (255 char max). User's first name. Required.
last_name: Free form text (255 char max). User's last name. Required.
military_status: none, service_member, veteran, retired_military, military_spouse_family. User's military status.
estimated_separation_on: Date in the form of yyyy-mm-dd. Estimated date on which the user will separate from the military. (Deprecated. Will be removed in the next version.)
rank: O-10 O-9 O-8 O-7 O-6 O-5 O-4 O-3 O-2 O-1 W-5 W-4 W-3 W-2 W-1 E-9 E-8 E-7 E-6 E-5 E-4 E-3 E-2 E-1 (Deprecated. Will be removed in the next version.)
service: air_force, air_force_reserve, air_national_guard, army, army_national_guard, army_reserve, coast_guard, coast_guard_reserve, marine_corps, marine_corps_reserve, navy, navy_reserve. Branch of service. Required. (Deprecated. Will be removed in the next version.)
moc_code: Free form text. A single MOC code that describes the user. Required. (Deprecated. Will be removed in the next version.)
security_clearance: decline_to_answer, inactive, active. User's security clearance.
military_installation: Free form text (255 char max). Military base the user is stationed at. (Deprecated. Will be removed in the next version.)
resume_url: URL of the resume file. Read only.
resume_file_name: File name of the resume. Read only.
resume_file_size: Size of the resume in bytes. Read only.
resume_content_type: Content type of the resume. Read only.
resume_updated_at: Last modified datetime of the resume. Read only.
education_level: some_college_courses, associates_degree, bachelors_degree, post_baccalaureate_certificate, masters_degree, post_masters_certificate, first_professional_degree, doctoral_degree. Maximum achieved education by the user. Required.
total_career_experience: none, one_to_two_years, three_to_five_years, six_to_ten_years, eleven_to_twenty_years, twenty_plus_years. Year range of total experience the user has. (Deprecated. Will be removed in the next version.)
career_level: entry_student, entry_non_student, experienced, mid_level_manager, manager, executive, senior_executive, other. Stage of user's career.
minimum_salary: 10000_dollars, 20000_dollars, 30000_dollars, 40000_dollars, 50000_dollars, 60000_dollars, 70000_dollars, 80000_dollars, 90000_dollars. Minimum salary the user is interested in making. (Deprecated. Will be removed in the next version.)
summary: Free form text (255 char max). (Deprecated. Will be removed in the next version.)
keywords: Free form text (no limit). Random buzz-words. (Deprecated. Will be removed in the next version.)
street1: Free form text (255 char max).
street2: Free form text (255 char max).
city: Free form text (255 char max).
state: Two letter state abbrv.  'NC, FL, MA'
postal_code: Free form text (255 char max). Required.
contact_number: Free form text (255 char max). User's phone number
relocation: Boolean. Is the user willing to relocate for a job?
job_type: full_time, part_time, internship, contractor. Type of job the user would like. (Deprecated. Will be removed in the next version.)
civilian_history: Array of civilian_history structures, definied below.  May be empty.
military_history: Array of military_history structures, definied below.  May be empty.

POST the portfolio json structured like above to create a portfolio for a user. PUT an updated json to edit.

Civilian and Military history are included in a GET, but are ignored in a PUT or POST, as they're updated with a separate API, below:


Civilian History json (POST /api/v3/portfolio/civilian_histories)
                      (PUT /api/v3/portfolio/civilian_histories/:id)
                      (DELETE /api/v3/portfolio/civilian_histories/:id)

POST and PUT return the full Profile json or an errors array.  Delete returns just a status code.

Civilian History:

id: Int, used to reference previously created history for PUT/DELETE.
description: Free form text or basic sanitized HTML (no limit).  Description of civilian job.
job_title: Free form text (255 char max).
started_on: Date (YYYY-MM-DD).
ended_on: Date (YYYY-MM-DD).
job_function: accounting_finance_insurance administrative_clerical banking_real_estate_mortgage construction_skill_trades business_strategic_management creative_design customer_support_client_care editorial_writing education_training engineering food_services hospitality human_resources installation_maintenance_repair it research_and_development software_development legal logistics_transportation manufacturing_production_operations marketing medical_health project_program_management quality_assurance sales_retail_business_development retail_business_development security_protective_services. (Deprecated. Will be removed in the next version.)
company_name: Free form text (255 char max).
city: Free form text (255 char max).
state: Two letter state abbrv.  "NC" "FL" "MA"

Military History json (POST /api/v3/portfolio/military_histories)
                      (PUT /api/v3/portfolio/military_histories/:id)
                      (DELETE /api/v3/portfolio/military_histories/:id)

POST and PUT return the full Profile json or an errors array.  Delete returns just a status code.

Military History:

id: Int, used to reference previously created history for PUT/DELETE.
description: Free form text or basic sanitized HTML (no limit).  Description of military job.
branch: air_force, air_force_reserve, air_national_guard, army, army_national_guard, army_reserve, coast_guard, coast_guard_reserve, marine_corps, marine_corps_reserve, navy, navy_reserve. Branch of service.
started_on: Date (YYYY-MM-DD).
ended_on: Date (YYYY-MM-DD).
rank: O-10 O-9 O-8 O-7 O-6 O-5 O-4 O-3 O-2 O-1 W-5 W-4 W-3 W-2 W-1 E-9 E-8 E-7 E-6 E-5 E-4 E-3 E-2 E-1
moc: Free form text. A single MOC code that describes the history.
service_field: air_defense_artillery adjutant_general army_nurse_corps armor aviation civil_affairs chaplains chemical dental_corps engineer field_artillery finance infantry judge_advocate_general medical_corps medical_service_corps military_intelligence military_police ordnance psychological_operations quartermaster signal special_forces army_medical_specialist_corps transportation veterinary_corps
city: Free form text (255 char max).
state: Two letter state abbrv.  "NC" "FL" "MA"
