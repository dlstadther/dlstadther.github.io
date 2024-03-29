# dlstadther.github.io

# Personal Homepage

Used to investigate github pages and jekyll.


## Blog Post Ideas
* Python
    * ~~Python3 Feature Excitement~~
    * Interview Problems
    * Spotify/Luigi: Real-world ETL Usage and Installation Guide
    * Simple REST API, using Flask or Django
    * ~~Managing multiple Python versions with pyenv~~
* DevOps
    * Deployment strategy and mistakes
        * Ansible + Jenkins Pipeline
    * Attempt at K8s
* Database
    * Database vs Data Warehouse
    * When to use sqlalchemy, local db, or remote db
    * Attempt with Redis, RethinkDB, and MongoDB
    * SQL: Group By vs Window Functions
* Projects
    * blog framework/hosting comparison + implementation
        * ~~GH Pages~~
        * GL Pages
        * S3 + Cloudfront + Route 53
* Other Technical
    * IDE vs Text Editor - why i prefer PyCharm over Sublime Text
    * ~~Zero to Maintainer - Reflection on role with Luigi~~
* Non-Technical (outside of code)
    * Disc Golf
        * strategy, nature impact, pictures
        * ~~pvc disc storage shelf~~
    * Hangboard Carpentry + Design + Engineering
        * ~~design + build~~
        * calculate theoretical max weight strength


## Setup instructions

```shell
# install ruby version manager
curl -sSL https://get.rvm.io | bash -s stable
rvm reload

# install latest ruby
rvm list known
rvm install 3.0.0

# check version
ruby -v

# update bundler
bundle update --bundler

# update packages
bundle update

# https://github.com/eventmachine/eventmachine/issues/932
# if error installing `eventmachine`, do the following:
brew install openssl
gem install eventmachine -- --with-openssl-dir=/usr/local/opt/openssl@1.1
bundle update

# if running into issues, remove gemlock
rm Gemfile.lock
bundle update
bundle install

# run local
bundle exec jekyll serve

# if running ruby 3.0.0, also install webrick
bundle add webrick
```
