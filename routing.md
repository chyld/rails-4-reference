### Routing

http://api.rubyonrails.org/classes/ActionDispatch/Routing.html

```ruby
Rails.application.routes.draw do
  root 'home#index'
  get '/hydrogen/:x/:y', to: 'home#hydrogen', as: 'h'
  post '/helium', to: 'home#helium', as: 'he'
  namespace :beryllium do
    resources :users do
      resources :tracks
      member do
        get 'eat'
        post 'run'
      end
      collection do
        put 'gather'
        patch 'follow'
      end
    end
  end
end
```
