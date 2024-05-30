
When you are pulling data in and out of a database, it is important to keep track of what you've changed, otherwise, data won't be written back do the database. Similarly you have to insert new objects you create and remove any objects you delete.

You can change the database with each change to  your object model, but this can lead to lots of very small database calls, which is not efficient. Furthermore it requires you to have a transaction open for the whole interaction.

**A unit of work is an object that keeps track of everything you do during a business transaction that can affect the database. When you're done, it figures out everything that needs to be done to alter the database as a result of your work.**
