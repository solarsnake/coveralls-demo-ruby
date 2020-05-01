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

This project is configured to send test coverage results to Coveralls through CircleCI.<sup>*</sup>

<details>
   <summary>* <em>How do we know it's working?</em></summary>

---

<Add content here.>

---

</details>

This guide will walk you through the configuration process.

## How to use this guide

Fork the master branch of this project and make your changes to your fork.<sup>*</sup>

<details>
   <summary>* <em>How do I do that?</em></summary>

---

<Add content here.>

---

</details>

After forking the project, keep this window open and refer back to the code in this branch to verify the changes you've made. (Consider it your cheatsheet.)

## Config steps

1. Add repo to CircleCI
2. Add `.circle/config.yml` to repo
3. Add repo to Coveralls
4. Finish coveralls setup

### 1. Add repo to CircleCI

<details>
   <summary>Do it. </summary>

---

<Add content here.>

---

</details>

### 2. Add `.circle/config.yml` to repo

<details>
   <summary>Do it. </summary>

---

<Add content here.>

---

</details>

### 3. Add repo to Coveralls

<details>
   <summary>Do it. </summary>

---

<Add content here.>

---

</details>

### 4. Finish coveralls setup

<details>
   <summary>Do it. </summary>

---

<Add content here.>

---

</details>

# Get badged <img src="../media/media/coveralls-badge-80-percent.png" width="99px" height="20px">

<details>
   <summary>Do it. </summary>

---

<Add content here.>

---

</details>

# Verify changes in test coverage via Coveralls <img src="../media/media/coveralls-badge-100-percent.png" width="106px" height="20px">

<details>
   <summary>Do it. </summary>

---

<Add content here.>

---

</details>

## More

- [ ] Section: Set up PR Comments - PRs vs pushes, and how to read results.
- [ ] Section: Links to other, more complicated CircleCI scenarios (parallel builds, etc.)

---

[WIP]

#### Setup Notes / Steps
- [x] Add [`simplecov-lcov`](https://github.com/fortissimo1997/simplecov-lcov) gem and convert test coverage report into lcov format to use coveralls orb
- [x] Add [coveralls orb](https://circleci.com/orbs/registry/orb/coveralls/coveralls)
- [x] Configure orb's upload command with parameters: path_to_lcov & token
- [ ] Embed coverage badge (and probably circleci badge)
- [ ] Write README
