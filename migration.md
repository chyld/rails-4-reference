### Migration

```ruby
def change
  create_table :tasks do |t|
    t.string :title, limit: 100, null: false
    t.datetime :due, null: false
    t.boolean :is_complete, null: false, default: false
    t.references :priority, index:true, null: false
    t.timestamps null: false
  end

  add_foreign_key :tasks, :priorities
end

def change
  create_table :movies do |t|
    t.string :name, limit: 25, null: false, index: true
    t.integer :year
  end

  create_table :actors do |t|
    t.string :name, limit: 25, null: false, index: true
    t.integer :age
  end

  create_table :actors_movies, id: false do |t|
    t.references :actor, index: true, null: false
    t.references :movie, index: true, null: false
  end

  add_foreign_key :actors_movies, :actors
  add_foreign_key :actors_movies, :movies
end
```
