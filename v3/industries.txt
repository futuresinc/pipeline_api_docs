GET /api/v3/industries

Returns array of parent industry hashes.

name: name of industry
id: unique id, can be used to fetch individual industry details


/api/v3/industries/<id>

Returns industry hash, as above with additional fields:

description:  Long description of industry
education:  Types of education generally associated with the industry
parent_id: id of parent industry or null if this industry is a parent
sub_industry_ids:  array of integer ids for child industries of this one
related_careers:  array of hashes, see careers.txt
