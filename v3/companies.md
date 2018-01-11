# Companies

## Object Definitions

Company
---
```
{ 
  id: String
  name: String
  company_type: String (nullable)
  company_size: String (nullable)
  vision: String (nullable)
  description: String (nullable)
  website: String (nullable)
  industry: String (nullable)
  address_city: String (nullable)
  address_state: String (nullable)
}
```

## Endpoints

## GET /api/v3/companies/:id (authenticated with guest support)

Note: Guest requests will always show 'favorite: false'.

### Params:
```
id: Int
# required, the id of the company to show.
```

### Returns:
```
{
  company: Company
  favorite: Bool
}
```

## PUT /api/v3/companies/:id/favorite (authenticated)

Create a favorite for this company.

### Returns:
204 response

## DELETE /api/v3/companies/:id/favorite (authenticated)

### Returns:
204 response
