# VanCamp

- rent your awesome van to awesome people
- airbnb clone project build at [lewagon coding bootcamp](https://www.lewagon.com/berlin)
- website can be checked out here: https://vancamp.herokuapp.com/

<a href="https://vancamp.herokuapp.com/"></a><img src="https://cdn.dribbble.com/users/31348/screenshots/5808409/311_reno_dkng_foil.jpg" width="400px"></a>


### Notes
```bash
# create rails app (with le wagon minimal rails app template: https://github.com/lewagon/rails-templates#minimal)
rails new \
  --database postgresql \
  --webpack \
  -m https://raw.githubusercontent.com/lewagon/rails-templates/master/minimal.rb \
  VanCamp

# Add to Gemfile (at the end)
gem 'devise'

# install gems
bundle install

# install devise
rails generate devise:install

# manually changed some files. Follow these two instruction slides:
# https://kitt.lewagon.com/karr/lectures/rails/authentication/index.html?title=Authentication#/3/2
# https://kitt.lewagon.com/karr/lectures/rails/authentication/index.html?title=Authentication#/3/3

# generate user model with devise gem
rails generate devise User

# migrate database to create users table
rails db:migrate

# generate vans model with description, location, brand, category, seats, user_id
rails g model van description location brand category seats:integer user:references

# create database
rails db:create

# migrate database
rails db:migrate

# generating a booking model w/ attributes van_id, user_id. checkin, checkout.
rails g model booking van:references user:references checkin:date checkout:date

# adding random change
```

Rails app generated with [lewagon/rails-templates](https://github.com/lewagon/rails-templates), created by the [Le Wagon coding bootcamp](https://www.lewagon.com) team.
