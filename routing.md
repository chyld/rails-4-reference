### Routing

http://api.rubyonrails.org/classes/ActionDispatch/Routing.html

```ruby
resources :photos

resources :magazines do
  resources :ads
end

namespace "admin" do
  resources :posts, :comments
end

scope path: "/cpanel", as: 'admin' do
  resources :posts, :comments
end

get 'post/:id' => 'posts#show'
post 'post/:id' => 'posts#create_comment'
match 'post/:id' => 'posts#show', via: [:get, :post]
```
