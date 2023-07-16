
# Drupal with Pantheon

## Go to pantheon create your site and clone it using git in you local.

Change directory into the site repository and verify your connection to the Pantheon server:

ex:-
cd d7-ci

git remote -v

origin  ssh://codeserver.dev.UUID@codeserver.dev.UUID.drush.in:2222/~/repository.git (fetch)

origin  ssh://codeserver.dev.UUID@codeserver.dev.UUID.drush.in:2222/~/repository.git (push)

## After cloning in local do:-
i.  ddev config

ii. ddev composer install

iii. ddev start

## Create a Repository on GitHub
Add the GitHub Repository as a Remote

### Ex:-
git remote add github git@github.com:pantheon-learning/d7-ci.git
git remote -v
github  git@github.com:pantheon-learning/d7-ci.git (fetch)
github  git@github.com:pantheon-learning/d7-ci.git (push)

origin  ssh://codeserver.dev.UUID@codeserver.dev.UUID.drush.in:2222/~/repository.git (fetch)

origin  ssh://codeserver.dev.UUID@codeserver.dev.UUID.drush.in:2222/~/repository.git (push)

## Push the Pantheon Site's Codebase to GitHub
Run the command below in your terminal:

### Push to github:-

git push -u github master


### Push to Pantheon:-

git push origin master

### Rename the remote repository:

git remote rename origin pantheon [For Pantheon]

git remote rename github origin [For Github]

## Deploy to Pantheon
Checkout the master branch on your local.

Pull from github master > push to pantheon master:

git checkout master
git pull github master
git push pantheon master


# Install Terminus

### You can get a list of all available commands:

terminus list

Automatic Site and Environment Detection
Terminus automatically detects the site and environment if a <site>.<env> parameter is not provided to a command that requests one. Terminus detects and operates from the local copy and current branch of the Pantheon site checked out at the current working directory.

### Ex:-
git clone ssh://codeserver.dev.UUID@codeserver.dev.UUID.drush.in:2222/~/repository.git mysite
cd mysite
terminus env:info

# Drush and WP-CLI
Pantheon supports Drush (Drupal) and WP-CLI (WordPress) commands remotely against a target site environment through Terminus. This is often faster and easier than leveraging such tools via local installations.

Use the basic command structure described above.

The commands to invoke Drush and WP-CLI are:

### remote:drush
### remote:wp

# Deploy Code
You can use Terminus to test a new set of changes by deploying code from development environments up to the Test environment while pulling the database and files down from Live.

Run the command below to deploy the code:

### terminus env:deploy my-site.test --sync-content --note="Deploy core and contrib 


For more information:-

Pantheon:- https://docs.pantheon.io/guides/git/git-config

Terminus:- https://docs.pantheon.io/terminus/examples




