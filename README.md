# Welcome to Rails 6 Send Mail Backgtound Job with gem sidekiq

The Rails 6  Send Mail Backgtound Job is a small task for everyone to practice more when programming with Ruby on Rails.

We will use gem sidekiq to perform this task.

## Support for me
Support this project :stuck_out_tongue_winking_eye: :pray:
<p align="center">
    <a href="https://www.paypal.me/tanhongcom" target="_blank"><img src="https://img.shields.io/badge/Donate-PayPal-green.svg" data-origin="https://img.shields.io/badge/Donate-PayPal-green.svg" alt="PayPal buymeacoffee TanHongIT"></a>
</p>

# 1. Technology
- Ruby on Rails

# 2. Configuration requirements
We are going to build the web application using:
- Rails 6.0.3.2
- Ruby 2.7.1

# 4. What is background Job
Since you already know the call to your Application will be slow, you want it to happen in a background job, so that users can see the confirmation message in their browser immediately without having to wait for the charge to actually happen. To do this, you must create an Active Job class, implement that class to call charge!(), and then add code to the controller to execute this job. The flow looks like the following figure.

![Image](https://imgur.com/Ns3P04e.png)

# 5. Runing

## 5.1. Clone Repo

```
$ git clone https://github.com/TanHongIT/send_mail_background_job
$ cd send_mail_background_job
```

### 5.2. Bundle Install 

```
$ bundle install
```

### 5.3. Yarn Install 

```
$ yarn install
```

### 5.4. Create database with Postgresql

You must change the appropriate database configuration

Change configuration at _"config/database.yml"_ with Postgresql.

```ruby
default: &default
  adapter: postgresql
  pool: <%= ENV.fetch("RAILS_MAX_THREADS") { 5 } %>
  timeout: 5000
  username: send_mail_background_job
  password: 1234
  host: localhost

# tutorial for ubuntu linux:
# sudo -u postgres psql
# create user "send_mail_background_job" with password '1234';  
# create database "send_mail_background_job" owner "send_mail_background_job"; 

development:
  <<: *default
  database: send_mail_background_job

# Warning: The database defined as "test" will be erased and
# re-generated from your development database when you run "rake".
# Do not set this db to the same as development or production.
test:
  <<: *default
  database: send_mail_background_job_test

production:
  <<: *default
  database: send_mail_background_job_production
```

You must change the username, password and database name accordingly!

### 5.5. run rails db:migrate

```
$ rails db:migrate
```

### 5.6. Change your mail

Run console :

```
$ bundle exec figaro install
```

Go to config directory and add to file **"config/application.yml"**

```ruby
user_mail: 'yourmail@gmail.com'
password: 'your password'
```

Change your mail in **app/mailers/application_mailer.rb** 

```ruby
class ApplicationMailer < ActionMailer::Base
  default from: 'your_mail'
  layout 'mailer'
end
```

### 5.7. Run sidekiq

```
$ bundle exec sidekiq
```

### 5.8. Run server 

Open new terminal and run:

```
rails s
```

Now go to at http://localhost:3000/users/new and put your mail end waiting for a response to arrive

# 6. Demo

![Image](https://imgur.com/xON93Xa.png)

<p align="center">
     <img src="https://img.shields.io/packagist/l/doctrine/orm.svg" data-origin="https://img.shields.io/packagist/l/doctrine/orm.svg" alt="license">
</p>
