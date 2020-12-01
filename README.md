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

* Go into the `tests/spec/` directory on your local machine and run:
```ruby
rake spec
```
* All tests should pass (vagrant machine must be up)


### Jenkins

* First, add this repo to GitHub (if not already on it)
*
