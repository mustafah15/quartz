---
tags:
  - database
parent: "[[database read phenomenas]]"
type: permanent
folgezettel: 3a2g4a
deeper:
---
what is a dirty read?
- is the state of reading uncommitted data. In this circumstance, we are not sure about the consistency of the data that is read because we don’t know the result of the open transaction(s). After reading the uncommitted data, the open transaction can be completed with a rollback or the open transaction can complete its actions successfully.