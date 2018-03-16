# I have added docker support to this heroku sample application

This was a quick change just for test and fun!
Credentials are set at docker-compose.yml - please change them!!!

## deploying on ec2

```
sudo yum update -f
sudo yum install -f docker
sudo service docker start
sudo usermod -a -G docker ec2-user
sudo curl -L https://github.com/docker/compose/releases/download/1.19.0/docker-compose-`uname -s`-`uname -m` -o /bin/docker-compose
sudo chmod +x /bin/docker-compose
git clone https://github.com/felipeamarante/ruby-rails-sample.git
cd ruby-rails-sample/
docker-compose up -d
docker-compose run web rake db:create

```


# ruby-rails-sample

This is a simple Ruby app using the [Rails](http://rubyonrails.org) framework.

## Running Locally

Make sure you have [Ruby](https://www.ruby-lang.org), [Bundler](http://bundler.io) and the [Heroku Toolbelt](https://toolbelt.heroku.com/) installed.

```sh
git clone git@github.com:heroku/ruby-rails-sample.git # or clone your own fork
cd ruby-rails-sample
bundle
bundle exec rake bootstrap
heroku local
```

Your app should now be running on [localhost:5000](http://localhost:5000/).

## Deploying to Heroku

```
heroku create
git push heroku master
heroku run rake db:migrate
heroku open
```

Alternatively, you can deploy your own copy of the app using the web-based flow:

[![Deploy to Heroku](https://www.herokucdn.com/deploy/button.png)](https://heroku.com/deploy)

## Documentation

For more information about using Ruby on Heroku, see these Dev Center articles:

- [Ruby on Heroku](https://devcenter.heroku.com/categories/ruby)
- [Getting Started with Ruby on Heroku](https://devcenter.heroku.com/articles/getting-started-with-ruby)
- [Heroku Ruby Support](https://devcenter.heroku.com/articles/ruby-support)
