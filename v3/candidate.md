# Candidate Search

This is for the searching of job seekers using keywords and other specific search criteria. A developer token will need to be obtained from Futures and will need to be submitted with each request in the query parameter `token`.


## Available search criteria

* `keywords` Keywords used in the profile.
* `location` City, State, or Postal code.
* `distance` Distance in miles from `location`.
* `job_type` One of `full_time` `part_time`.
* `military_status` One of `service_member` `veteran` `retired_military` `military_spouse_family`.
* `last_activity` Time period in which the user was last active on the site. One of `since_yesterday` `last_3_days` `last_week` `last_15_days` `last_30_days` `last_60_days` `last_90_days`.
* `estimated_separation` Estimated date by which a user will be available for employment. Should be in ISO 8601 format.
* `moc_codes` MOC/MOS code which associated to a user.
* `member_sites` Site hostname that the user signed-up on or logged into.
* `last_activity_date` Filters out all users who were last active before this date.
* `branch` Branch of military service. One of `air_force` `air_force_reserve` `air_national_guard` `army` `army_national_guard` `army_reserve` `coast_guard` `coast_guard_reserve` `marine_corps` `marine_corps_reserve` `navy` `navy_reserve`.
* `minimum_rank` Minimum military rank. One of `E-1` `E-2` `E-3` `E-4` `E-5` `E-6` `E-7` `E-8` `E-9` `W-1` `W-2` `W-3` `W-4` `W-5` `O-1` `O-2` `O-3` `O-4` `O-5` `O-6` `O-7` `O-8` `O-9` `O-10`.
* `maximum_rank` Maximum military rank. One of `E-1` `E-2` `E-3` `E-4` `E-5` `E-6` `E-7` `E-8` `E-9` `W-1` `W-2` `W-3` `W-4` `W-5` `O-1` `O-2` `O-3` `O-4` `O-5` `O-6` `O-7` `O-8` `O-9` `O-10`.
* `minimum_security_clearance` Minimum security clearance. One of `inactive_confidential` `inactive_secret` `inactive_top_secret_or_higher` `active_confidential` `active_secret` `active_top_secret` `active_top_secret_sci_or_higher`.
* `maximum_security_clearance` Maximum security clearance. One of `inactive_confidential` `inactive_secret` `inactive_top_secret_or_higher` `active_confidential` `active_secret` `active_top_secret` `active_top_secret_sci_or_higher`.
* `minimum_education_level` One of `less_than_a_high_school_diploma` `high_school_diploma` `post_secondary_certificate` `some_college_courses` `associates_degree` `bachelors_degree` `post_baccalaureate_certificate` `masters_degree` `post_masters_certificate` `first_professional_degree` `doctoral_degree` `post_doctoral_training`.
* `maximum_education_level` One of `less_than_a_high_school_diploma` `high_school_diploma` `post_secondary_certificate` `some_college_courses` `associates_degree` `bachelors_degree` `post_baccalaureate_certificate` `masters_degree` `post_masters_certificate` `first_professional_degree` `doctoral_degree` `post_doctoral_training`.
* `minimum_career_level` One of `entry_student` `entry_non_student` `some_work_experience` `experienced` `mid_level_manager` `manager` `executive` `senior_executive` `other`.
* `maximum_career_level` One of `entry_student` `entry_non_student` `some_work_experience` `experienced` `mid_level_manager` `manager` `executive` `senior_executive` `other`.
* `availability_date` Return users that have stated that they will be available by this date. Should be in ISO 8601 format.
* `citizenship` One of `us_citizen` `non_us_citizen` `can_only_work_for_current_employer` `need_sponsorship`.
* `relocation` Set to '1' to only return users willing to relocate. Set to '0' to only return users not willing to relocate.
* `languages` Return users that speak these languages. One of `spanish` `french` `german` `chinese_mandarin` `chinese_cantonese_other` `hindi_urdu` `arabic` `bengali` `portuguese` `russian` `japanese` `punjabi` `african_dialects` `other_asian` `other_middle_eastern` `other_eastern_european`.

## Examples Requests

Criteria should be submitted as query parameters.

* `GET /candidates/search?keywords=experienced&moc_codes=11b` returns the jobs seekers that have the moc/mos code of '11b' and match the keyword of 'experienced'.
* `GET /candidates/search?member_sites=pipeline.futuresinc.com` returns only the jobs seekers who have signed up on Pipeline.

## Example Response

Results will be paginated in groups of 10. The response will be in json. The total number of pages will be returned as a root key named `total_pages`. The results will be under a root key named `results`.

Only two results are shown for brevity.

```json
{
  "total_pages":9,
  "results":[
    {
      "id":71461,
      "email":"DG71461@example.com",
      "first_name":"Damon",
      "last_name":"G",
      "available_on":"2012-05-24",
      "relocation":false,
      "city":"ATL",
      "state":"GA",
      "postal_code":"30316",
      "last_activity":"2012-05-24"
    },
    {
      "id":53999,
      "email":"SG53999@example.com",
      "first_name":"Scott",
      "last_name":"G",
      "available_on":"2012-05-15",
      "relocation":false,
      "city":"West Haven",
      "state":"CT",
      "postal_code":"06516",
      "last_activity":"2012-03-26"
    }
  ]
}
```
