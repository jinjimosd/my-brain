1. Create user
```sh
// Switch to the admin database
use admin

// Create the user with readWriteAnyDatabase role
db.createUser({
  user: "yourUsername",
  pwd: "passwordPrompt()",
  roles: [
    { role: "readWriteAnyDatabase", db: "admin" }
  ]
})

db.createUser({
  user: "thedt",
  pwd: "cl1EG22AA2f6PPfT",
  roles: [
    { role: "readWriteAnyDatabase", db: "admin" }
  ]
})

db.createUser({
  user: "bangdv",
  pwd: "cl1EG22AA2f6PPfT",
  roles: [
    { role: "readWriteAnyDatabase", db: "admin" }
  ]
})

```