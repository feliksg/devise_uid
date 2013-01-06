# devise_uid

[![Dependency
Status](https://gemnasium.com/jingweno/devise_uid.png)](https://gemnasium.com/jingweno/devise_uid)

Add UID stupport to Devise.

## Installation

Add this line to your application's Gemfile:

    gem 'devise'
    gem 'devise_uid'

And then execute:

    $ bundle

### Automatic Installation

Add devise_uid to any of your Devise models using the
following generator:

    rails generate devise_uid MODEL

Replace MODEL with the class name you want to add devise_uid.
This will add the :uid flag to your model's Devise modules.
The generator will also create a migration file.
Currently only ActiveRecord is supported.

### Manual Installation

Add `:uid` to the `devise` call in your model:

```ruby
class User < ActiveRecord
  devise :database_authenticable, :confirmable, :uid
end
```

Add `uid` field to your Devise model migration:

```ruby
class AddUidToUser< ActiveRecord::Migration
  add_column :users, :uid, :string
  add_index :users, :uid, :unique => true
end
```

## Usage

An uid is generated when a Devise MODEL is created. Access it like this:

```ruby
user = User.create(email: "foo@bar.com")
puts user.uid
```

## Contributing

1. Fork it
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Commit your changes (`git commit -am 'Add some feature'`)
4. Push to the branch (`git push origin my-new-feature`)
5. Create new Pull Request
