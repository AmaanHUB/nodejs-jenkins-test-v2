# NodeJS Sample App Development Environment and CI (with Jenkins)

This repo will be a development environment one can copy and setup by running vagrant up

## Requisites
* Virtual box
* Git
* Ruby
	* `bundler` gem
* Vagrant


## Instructions

* Install the relevant requisites with the relevant package manager on your distribution
* Clone the git directory with the `git clone` command
* Move into the directory (with `cd`)
* `vagrant up`
* **Ta-dah, your dev environment will be set up momentarily**
* The app will be on `development.local` in your web browser
* Fibonacci index will be on `development.local/fibonacci/<index>` where `<index>` is a number of your choice
* The posts/blog will be on `development.local/posts`

### Local Testing

#### Part I
* Go into the `tests/spec/` directory on your local machine and run:
```sh
rake spec
```
* All tests should pass (vagrant machine must be up)

#### Part II
* `ssh` into the `app` VM
* Change to the directory that contains the app
* Run:
```sh
npm test
```
* All tests should pass
	* The Blogs one will not since it only seems to work when called with `npm start` and does not recognise `pm2 start app`, though `pm2` is a better way to run these sorts of things (makes it easier to stop and start etc)


### Jenkins

//TODO (maybe), setting up Jenkins with webhooks and perhaps Teams integration

// Something about email too
:chicken:
:zap:
