### DB Tasks


```sh
bin/rake db:migrate VERSION=20080906120000
bin/rake db:rollback STEP=3
bin/rake db:migrate:redo STEP=3

rake db:create                          # Creates the database from DATABASE_URL or config/datab...
rake db:drop                            # Drops the database from DATABASE_URL or config/databas...
rake db:fixtures:load                   # Load fixtures into the current environment's database
rake db:migrate                         # Migrate the database (options: VERSION=x, VERBOSE=fals...
rake db:migrate:status                  # Display status of migrations
rake db:rollback                        # Rolls the schema back to the previous version (specify...
rake db:schema:cache:clear              # Clear a db/schema_cache.dump file
rake db:schema:cache:dump               # Create a db/schema_cache.dump file
rake db:schema:dump                     # Create a db/schema.rb file that is portable against an...
rake db:schema:load                     # Load a schema.rb file into the database
rake db:seed                            # Load the seed data from db/seeds.rb
rake db:setup                           # Create the database, load the schema, and initialize w...
rake db:structure:dump                  # Dump the database structure to db/structure.sql
rake db:structure:load                  # Recreate the databases from the structure.sql file
rake db:version                         # Retrieves the current schema version number
```
