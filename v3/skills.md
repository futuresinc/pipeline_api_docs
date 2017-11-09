# Skills

## Object Definitions

Skill
---
```
{ "uuid": String, "skill_type": SkillType, "name": String }
```

SkillType (enum)
---
```
S (Skill)
B (...Basic?)
C (Certificate)
L (License)
```

## Endpoints

## GET /api/v3/related_skills (authenticated)

### Params:
```
job_titles: [ String ]
# optional, default: current_user’s job titles

moc_uuids: [ String ]
# optional, default: current_user’s moc_uuids

limit: Integer
# optional, default: 20
```

### Returns:
```
[ Skill ]
```

## GET /api/v3/search_skills (authenticated)

### Params:
```
keywords: String
# optional, default: current_user's job titles
# Space-delimited.
# The keywords are combined using AND.

certs_and_licenses: Boolean 
# optional, default: false
# If true, searches only Certs + Licenses. If false, searches only Skills.

limit: Integer
# optional, default: 20
```

### Returns:
```
[ Skill ]
```

