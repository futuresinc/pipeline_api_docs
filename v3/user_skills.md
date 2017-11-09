# UserSkills

## Object Definitions

UserSkill
---
```
{ "id": Integer, "experience": UserSkillExperience, "skill": Skill }
```

UserSkillExperience
---
```
one_to_two_years
three_to_five_years
six_to_ten_years
ten_plus_years
any
```

## Endpoints

## GET /api/v3/user_skills (authenticated)

### Returns:
```
[ UserSkill ]
```

## POST /api/v3/user_skills (authenticated)

### Params:
```
"skill_id": String
# required

"experience": UserSkillExperience
# optional, default: nil
```

### Returns:
```
UserSkill
```

## PUT /api/v3/user_skills/:id (authenticated)

### Params:
```
"skill_id": String
# optional

"experience": UserExperience
# optional
```

### Returns:
```
UserSkill
```

## DELETE /api/v3/user_skills/:id (authenticated)

### Returns:
```
Status code 204
```
