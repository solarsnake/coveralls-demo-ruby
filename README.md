[![Coverage Status](https://coveralls.io/repos/github/afinetooth/coveralls-demo-ruby/badge.svg?branch=travis)](https://coveralls.io/github/afinetooth/coveralls-demo-ruby?branch=travis)

# coveralls-ruby-demo for Travis CI

[Coveralls](https://coveralls.io/) demo project, using:

* [Ruby](https://www.ruby-lang.org/) — *Language*
* [Rspec](https://rspec.info/) — *Testing Library*
* [Simplecov](https://github.com/colszowka/simplecov) — *Code Coverage Library*

And:

* [GitHub](https://github.com/) — *SCM Service*
* [Travis CI](https://travis-ci.com/) — *CI Service*
* [Coveralls](https://coveralls.io/) — *Test Coverage Service*

# Welcome

You've gotten this far. Given that, we can assume:
   
<dl>
  <dt>1. You understand <a href="https://github.com/afinetooth/coveralls-demo-ruby#1-understand-test-coverage-in-this-project">how test coverage works in this project</a>.</dt>
  <dd>If not, start back at the <a href="https://github.com/afinetooth/coveralls-demo-ruby">master README</a>.</dd>

  <dt>2. You've chosen <a href="https://travis-ci.com/">Travis CI</a> as your CI Service.</dt>
  <dd>If not, head back to the <a href="https://github.com/afinetooth/coveralls-demo-ruby">master README</a>, <a href="https://github.com/afinetooth/coveralls-demo-ruby#4-configure-this-project-to-use-coveralls">here</a>, and <a href="https://github.com/afinetooth/coveralls-demo-ruby#which-ci-service-will-you-use">choose a different CI service / branch</a>.</dd>
</dl>

# Travis CI & Coveralls

This project is configured to send test coverage results to [Coveralls](https://coveralls.io/) through [Travis CI](https://travis-ci.com/). 

Here's how it's done:

## Travis config steps

1. Add repo to [Travis CI](https://travis-ci.com/)
2. Add `.travis.yml` to repo
3. Add repo to [Coveralls](https://coveralls.io/)
4. Add `.coveralls.yml` to repo

### 1. Add repo to Travis CI

To add a public repo to Travis CI, you'll first need to sign up for the free version of the service, which you can do by going to [http://travis-ci.org/](http://travis-ci.org/) and singing up with your GitHub login:

[Travis CI - Sign Up]

Alternately, if you're already a member, just sign in with your GitHub login:

[Travis CI - Sign In]

Once signed in, click on [Settings](https://travis-ci.org/account/repositories) or go to [https://travis-ci.org/account/repositories](https://travis-ci.org/account/repositories):

[Travis CI - Settings - Repositories]

If Travis doesn't already list all your public repos<sup>*</sup>, click the __Sync account__ button to refresh the list.

<details>
   <summary><sup>*</sup> Looking to sync your private repos?</summary>

---

   [http://travis-ci.org/](http://travis-ci.org/) is the free version of the Travis CI service that's always free for public repos. To manage private repos, you'll want to join [http://travis-ci.com/](http://travis-ci.com/).
</details>

To add a repo to [Travis CI]((http://travis-ci.org/)), simply click the toggle control next to your repo:

[Travis Ci - Settings - Repositories - Add `coveralls-ruby-demo`]

WIP

### 2. Add `.travis.yml` to repo

WIP

### 3. Add repo to Coveralls

WIP

### 4. Add `.coveralls.yml` to repo

WIP

# To Do:
* Add Travis logo
* Add Coveralls logo
