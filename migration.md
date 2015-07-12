### Migration

```ruby
class CreateTasks < ActiveRecord::Migration
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
end
```
