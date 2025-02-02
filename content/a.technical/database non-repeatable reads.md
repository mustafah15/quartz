---
tags:
  - database
parent: "[[database read phenomenas]]"
type: permanent
folgezettel: 3a2g4b
---
A non-repeatable read occurs when during the course of a transaction, a row is retrieved twice and the values within the row differ between reads caused by a successfully committed change.


The key to non-repeatable reading is to **modify**:  
In the same conditions, the data you have read, read it again, and find that the **value is different.**  
The key point of the [[database phantom reads]] is to **add** or **delete**:  
Under the same conditions, the **number of records** read out for the first time and the second time is different.

