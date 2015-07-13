### Faking Data

* https://github.com/stympy/faker
* https://github.com/sevenwire/forgery
* https://github.com/ffaker/ffaker

```sh
rails g task __namespace__ __taskname__
```

```ruby
namespace :chyld do
  desc "Populate database with fake data"
  task populate: :environment do
    User.delete_all

    1000.times do
      User.create({
        name: Faker::Name.name,
        gender: Forgery('personal').gender,
        weight: Faker::Number.between(100, 300),
        height: Faker::Number.between(50, 80),
        birthday: Faker::Date.between(20.years.ago, Date.today)
      })
      end

    first = User.order('id asc').limit(1).first.id
    last = User.order('id desc').limit(1).first.id

    puts "first #{first} --- last #{last}"

    1000.times do |i|
      u = User.find(first + i)
      u.manager_id = Faker::Number.between(first, last)
      u.save
    end
  end
end
```
