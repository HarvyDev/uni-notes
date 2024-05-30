Loading objects from a database can be messy. If you aren't careful, you can load the data from the same database record into two different objects. Related to this is an obvious performance issue. If you load the same data more than once you're incurring an expensive cost in remote calls. 

An Identity Map keeps a record of all objects that have been read from the database in a single business transaction. **Whenever you want an object, you check the Identity Map first o see if you already have it.**

