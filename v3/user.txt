User json (GET /api/v3/user):
{
  "first_name": "John",
  "last_name": "Dough",
  "email": "user@example.com"
}

Valid keys and values (w/ descriptions):
first_name: Free form text (255 char max). User's first name.
last_name: Free form text (255 char max). User's last name.
email: User's email address. Required.

POST the user json structured like above to create a new user. PUT an updated json to edit.

Additionally POSTs also require a "password" parameter that is the user's password to their account. A "password" can optionally be used on a PUT to change the existing password. POSTs and PUTs also optionally accept "password_confirmation" and "email_confirmation" that must match "password" and "email" respectively. Otherwise, the api call will not be successful and errors will be returned.
