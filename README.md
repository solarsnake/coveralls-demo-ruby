# coveralls-ruby-demo for CircleCI

[Coveralls](https://coveralls.io/) demo project, using:

* [Ruby](https://www.ruby-lang.org/) — *Language*
* [Rspec](https://rspec.info/) — *Testing Library*
* [Simplecov](https://github.com/colszowka/simplecov) — *Code Coverage Library*

And these services:

* [CircleCI](https://circleci.com/) — *CI Service*
* [Coveralls](https://coveralls.io/) — *Test Coverage Service*

# Welcome

If you've gotten this far, we can assume:

<dl>
  <dt>1. You understand <a href="https://github.com/afinetooth/coveralls-demo-ruby#1-understand-test-coverage-in-this-project">how test coverage works in this project</a>.</dt>
  <dd>If not, start back at the <a href="https://github.com/afinetooth/coveralls-demo-ruby">master README</a>.</dd>

  <dt>2. You've chosen <a href="https://circleci.com/">CircleCI</a> as your CI Service.</dt>
  <dd>If not, head back to the <a href="https://github.com/afinetooth/coveralls-demo-ruby">master README</a> and <a href="https://github.com/afinetooth/coveralls-demo-ruby#which-ci-service-will-you-use">choose a different CI / branch</a>.</dd>
</dl>

# Configure your project for Coveralls & CircleCI

[WIP]

### Setup Notes / Steps
- [x] Add [`simplecov-lcov`](https://github.com/fortissimo1997/simplecov-lcov) gem and convert test coverage report into lcov format to use coveralls orb
- [x] Add [coveralls orb](https://circleci.com/orbs/registry/orb/coveralls/coveralls)
- [x] Configure orb's upload command with parameters: path_to_lcov & token
- [ ] Embed coverage badge (and probably circleci badge)
- [ ] Write README
