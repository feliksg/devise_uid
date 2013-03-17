source 'https://rubygems.org'

# Specify your gem's dependencies in devise_uid.gemspec
gemspec

gem 'rails', '4.0.0.beta1'

group :test do
  gem "activerecord"

  platforms :jruby do
    gem "activerecord-jdbcsqlite3-adapter"
  end

  platforms :ruby do
    gem "sqlite3"
  end
end
