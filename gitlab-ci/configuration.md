# Ruby on Rails runner

```markdown
 stages:
 - test

 test:
   stage: test
   services:
   - postgres:12
   variables:
     POSTGRES_HOST_AUTH_METHOD: trust
   script:
   - source ~/.bashrc
   # ...
   # check installed ruby version with asdf
   # check installed bundler
   # ...
   - bundle install --path .bundle
   - export RAILS_ENV=test
   - export DATABASE_URL=postgres://postgres@postgres/<project_name>_test
   - export DATABASE_CLEANER_ALLOW_REMOTE_DATABASE_URL=true
   - bundle exec rake db:create db:migrate
   - bundle exec rake
   cache:
     key:
       files:
       - Gemfile.lock
     paths:
     - .bundle/
```
