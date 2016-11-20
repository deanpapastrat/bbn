# Bible Bowl Network (v2)

## Installing

There are 3 main components to the installation process for developers:

1. Install Homebrew or Linuxbrew
2. Install RVM and rubies
3. Install project dependencies
4. Setup the Rails application
5. Setup the Ember application

### Brew

Homebrew and Linuxbrew are package managers for Unix-based operating systems. They make setting up development environments and installing required packages super easy, including dependency management. They'll also allow us to use standardized insturctions for the rest of the install process.

#### macOS:

```
/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```

#### Linux:

```
ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Linuxbrew/install/master/install)"
```

### RVM and Rubies

We use RVM, Ruby Version Manager, to keep track of the current Ruby version. We try to operate on the latest stable version of Ruby, so this should generally work for you.

```
\curl -sSL https://get.rvm.io | bash -s stable --autolibs=homebrew
```

### Project Dependencies

#### Git

Git is a version-control system for source code.

```
brew install git
```

#### Yarn

```
brew install yarn
```

#### PostgreSQL

Postgres is a relational datastore.

```
brew install postgres
```

### Rails

Rails is the backend framework we're using to persist, manage, and query data. It uses Postgres as the primary datastore.

Inside the server directory, install Rails:

1. Install bundler `gem install bundler`
2. Install the gems for the project `bundle install`

### Ember

Ember is the client-side framework we're using to create the user interface and manage data in browser.

Inside the client directory, install Ember:

1. Install ember-cli `yarn global add ember-cli`
2. Install node modules `yarn install`
3. Install bower components `bower install`

**Awesome, you should be all set up and ready to go now!**

## Running

### Rails

Rails binds to `localhost:3000`.

#### First Run

```
rake db:setup
```

*If this doesn't work, do `gem install rake` first.*

#### Standard Run Command

```
rails s
```

*If this doesn't work, do `gem install rails` first.*

### Ember

We're going to proxy Ember's server side hits to Rails. This makes config much easier!

Ember binds to `localhost:4200`.

```
ember serve --proxy http://localhost:3000
```

**Don't hesistate to let us know if you have any questions or concerns!**
