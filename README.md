# Active Record Lite
Active Record takes a lot of the grunt work out of making database queries. To understand how the world of Rails' Active Record is translated into SQL, I built my own lite version of it.

Below are some noteworthy facets of this project:

* **MassObject**: [mass_object.rb](https://github.com/rrzein/ActiveRecordLite/blob/master/lib/active_record_lite/mass_object.rb)
  `MassObject` is the analogue of ActiveRecord's Base class. It creates a class that includes methods for parsing query results and initializing and setting attributes for model objects.

* **SQLObject**: [sql_object.rb](https://github.com/rrzein/ActiveRecordLite/blob/master/lib/active_record_lite/sql_object.rb)
  `SQLObject` is the interface between ActiveRecordLite and the SQL database. It searches the database along the user specified parameters as well as creates, updates, and saves new entries into the database.

* **Searchable** [searchable.rb](https://github.com/rrzein/ActiveRecordLite/blob/master/lib/active_record_lite/searchable.rb)
  `Searchable` extends the SQLObject class method, allowing users to perform Active Record's `where` feature to perform more specific database queries.

* **Associatable** [associatable.rb](https://github.com/rrzein/ActiveRecordLite/blob/master/lib/active_record_lite/associatable.rb)
  `Associatable` is the bread and butter of this Active Record "Lite" app. It defines `has_one`, `has_many`, `belongs_to`, and `has_one_through` associations between models and allows the user to perform the relevant database queries for associated models.