# Setup instructions

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
