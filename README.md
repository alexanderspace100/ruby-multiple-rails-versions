# How to Run Multiple Versions of Rails

This is the situation:

* You have some projects using rails 4
* You want to start a new rails 5 project

What to do?

* Install [``rvm``](https://rvm.io/rvm/install) if you are not using it
* Use the ``rvm`` ``gemsets`` option

## Steps to Use rvm gemset

### Check the Ruby Version

* Rails 5 requires ruby >= 2.2.2
* Gemsets are nested inside the ruby version
* Make sure Ruby >= 2.2.2 is being used
``$ rvm use ruby-2.2.2``

### Create new gemset

``$ rvm gemset create rails5gems``

```
ruby-2.2.0 - #gemset created /Users/stuart/.rvm/gems/ruby-2.2.0@rails5gems
ruby-2.2.0 - #generating rails5gems wrappers........
```

``$ rvm gemset use rails5gems``

```
Using ruby-2.2.0 with gemset rails5gems
```


``$ gem list``

```
*** LOCAL GEMS ***

bigdecimal (1.2.6)
bundler (1.11.2)
bundler-unload (1.0.2)
executable-hooks (1.3.2)
gem-wrappers (1.2.7)
io-console (0.4.3)
json (1.8.1)
minitest (5.4.3)
power_assert (0.2.2)
psych (2.0.8)
rake (10.4.2)
rdoc (4.2.0)
rubygems-bundler (1.4.4)
rvm (1.11.3.9)
test-unit (3.0.8)
```

### Install Rails 5 in the new gemset

Make sure we are using the rails5gems gemset

``$ rvm gemset use rails5gems``

```
Using /Users/stuart/.rvm/gems/ruby-2.2.2
```

Install the Rails Pre-Release (remove --pre if you are in the future...)

``$ gem install rails --pre``

```
Fetching: concurrent-ruby-1.0.1.gem (100%)
Successfully installed concurrent-ruby-1.0.1
Fetching: activesupport-5.0.0.beta3.gem (100%)
Successfully installed activesupport-5.0.0.beta3
Fetching: erubis-2.7.0.gem (100%)
Successfully installed erubis-2.7.0
Fetching: rails-deprecated_sanitizer-1.0.3.gem (100%)
Successfully installed rails-deprecated_sanitizer-1.0.3
Fetching: rails-dom-testing-1.0.7.gem (100%)
Successfully installed rails-dom-testing-1.0.7
Fetching: loofah-2.0.3.gem (100%)
Successfully installed loofah-2.0.3
Fetching: rails-html-sanitizer-1.0.3.gem (100%)
Successfully installed rails-html-sanitizer-1.0.3
Fetching: actionview-5.0.0.beta3.gem (100%)
Successfully installed actionview-5.0.0.beta3
Fetching: rack-2.0.0.alpha.gem (100%)
Successfully installed rack-2.0.0.alpha
Fetching: actionpack-5.0.0.beta3.gem (100%)
Successfully installed actionpack-5.0.0.beta3
Fetching: nio4r-1.2.1.gem (100%)
Building native extensions.  This could take a while...
Successfully installed nio4r-1.2.1
Fetching: websocket-extensions-0.1.2.gem (100%)
Successfully installed websocket-extensions-0.1.2
Fetching: websocket-driver-0.6.3.gem (100%)
Building native extensions.  This could take a while...
Successfully installed websocket-driver-0.6.3
Fetching: actioncable-5.0.0.beta3.gem (100%)
Successfully installed actioncable-5.0.0.beta3
Fetching: globalid-0.3.6.gem (100%)
Successfully installed globalid-0.3.6
Fetching: activejob-5.0.0.beta3.gem (100%)
Successfully installed activejob-5.0.0.beta3
Fetching: mail-2.6.4.gem (100%)
Successfully installed mail-2.6.4
Fetching: actionmailer-5.0.0.beta3.gem (100%)
Successfully installed actionmailer-5.0.0.beta3
Fetching: activemodel-5.0.0.beta3.gem (100%)
Successfully installed activemodel-5.0.0.beta3
Fetching: arel-7.0.0.gem (100%)
Successfully installed arel-7.0.0
Fetching: activerecord-5.0.0.beta3.gem (100%)
Successfully installed activerecord-5.0.0.beta3
Fetching: method_source-0.8.2.gem (100%)
Successfully installed method_source-0.8.2
Fetching: thor-0.19.1.gem (100%)
Successfully installed thor-0.19.1
Fetching: railties-5.0.0.beta3.gem (100%)
Successfully installed railties-5.0.0.beta3
Fetching: sprockets-3.6.0.gem (100%)
Successfully installed sprockets-3.6.0
Fetching: sprockets-rails-3.0.4.gem (100%)
Successfully installed sprockets-rails-3.0.4
Fetching: rails-5.0.0.beta3.gem (100%)
Successfully installed rails-5.0.0.beta3
27 gems installed
```

### Use Rails

``$ rails -v``

```
Rails 5.0.0.beta3
```

## Restore the default rvm gemset

``$ rvm gemset use default``

```
Using ruby-2.2.0 with gemset default
```

``$ rails -v``

If you didn't have rails installed for ruby 2.2.2, you'll see this:

*DO NOT FOLLOW THE INSTRUCTIONS to sudo anything :)*

```
Rails is not currently installed on this system. To get the latest version, simply type:

    $ xudo gem install rails
```
In which case you probably want to do this:

``$ rvm use default``

```
Using /Users/stuart/.rvm/gems/ruby-2.1.0
```

``$ rails -v``

```
Rails 4.2.4
```









 
