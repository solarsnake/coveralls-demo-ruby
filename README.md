[![Coverage Status](https://coveralls.io/repos/github/afinetooth/coveralls-demo-ruby/badge.svg?branch=travis)](https://coveralls.io/github/afinetooth/coveralls-demo-ruby?branch=travis)

# coveralls-ruby-demo for Travis CI

[Coveralls](https://coveralls.io/) demo project, using:

* [Ruby](https://www.ruby-lang.org/) — *Language*
* [Rspec](https://rspec.info/) — *Testing Library*
* [Simplecov](https://github.com/colszowka/simplecov) — *Code Coverage Library*

And:

* [GitHub](https://github.com/) — *SCM Service*
* [Travis CI](https://travis-ci.org/) — *CI Service*
* [Coveralls](https://coveralls.io/) — *Test Coverage Service*

# Welcome

If you've gotten this far, we can assume:
   
<dl>
  <dt>1. You understand <a href="https://github.com/afinetooth/coveralls-demo-ruby#1-understand-test-coverage-in-this-project">how test coverage works in this project</a>.</dt>
  <dd>If not, start back at the <a href="https://github.com/afinetooth/coveralls-demo-ruby">master README</a>.</dd>

  <dt>2. You've chosen <a href="https://travis-ci.org/">Travis CI</a> as your CI Service.</dt>
  <dd>If not, head back to the <a href="https://github.com/afinetooth/coveralls-demo-ruby">master README</a> and <a href="https://github.com/afinetooth/coveralls-demo-ruby#which-ci-service-will-you-use">choose a different CI / branch</a>.</dd>
</dl>

# Travis CI & Coveralls

This project is configured to send test coverage results to [Coveralls](https://coveralls.io/) through [Travis CI](https://travis-ci.org/).<sup>*</sup>

This guide will walk you through that configuration process.

<details>
   <summary><sup>*</sup> <em>How do we know?</em></summary>

---

Notice the Coveralls badge at the top of the page:

[![Coverage Status](https://coveralls.io/repos/github/afinetooth/coveralls-demo-ruby/badge.svg?branch=travis)](https://coveralls.io/github/afinetooth/coveralls-demo-ruby?branch=travis)

That tells us we're configured correctly and successfully receiving coverage reports from [Coveralls](https://coveralls.io/).

---

</details>

## How to use this guide

Fork the [master branch](https://github.com/afinetooth/coveralls-demo-ruby/tree/master) of this project<sup>*</sup> and make your changes to it. Then use *this branch* to verify the changes you'll make. (Consider it your cheatsheet.)

<details>
   <summary>* <em>How do I do that?</em></summary>
   
---

<em>How-to (WIP).</em>

---

</details>

## Config steps

1. Add repo to [Travis CI](https://travis-ci.org/)
2. Add `.travis.yml` to repo
3. Add repo to [Coveralls](https://coveralls.io/)
4. Add `.coveralls.yml` to repo

### 1. Add repo to Travis CI

<details>
   <summary><em>How?</em></summary>
   
---
   
To add a public repo to [Travis CI](http://travis-ci.org/), sign in<sup>*</sup> at [http://travis-ci.org/](http://travis-ci.org/) with your GitHub login:

![travis-ci-sign-in.png](../media/media/travis-ci-sign-in.png)

<details>
   <summary>* <em>Need to sign up?</em></summary>

---

Easy enough, just click <strong>Sign up</strong> and use your GitHub login:

![travis-ci-sign-up.png](../media/media/travis-ci-sign-up.png)

---
</details>

Once signed in, click on your profile on the uppper right and choose <strong>Settings</strong>, or go to [https://travis-ci.org/account/repositories](https://travis-ci.org/account/repositories):

![travis-ci-settings-repos.png](../media/media/travis-ci-settings-repos.png)

If Travis doesn't already list all your public repos<sup>*</sup>, click the __Sync account__ button to refresh the list.

<details>
   <summary>* <em>What about private repos?</em></summary>

---

<em><a href="http://travis-ci.org/">http://travis-ci.org/</a> is the free version of the Travis CI service that's always free for public repos. To manage private repos, you'll want to join <a href="http://travis-ci.com/">http://travis-ci.com/</a>.</em>
   
---

</details>

To add your repo to [Travis CI](http://travis-ci.org/), simply click the toggle control next to your repo, setting it to ON:

![travis-ci-settings-repos-coveralls-demo-ruby.png](../media/media/travis-ci-settings-repos-coveralls-demo-ruby.png)

<details>
   <summary><em>What about settings and stuff?</em></summary

<em>Not necessary at this point. You can click on <strong>Settings</strong> next to your repo to see some basic configuration options for your repo, but for now let's leave everything there as-is:</em>

![travis-ci-settings-repos-coveralls-demo-ruby-settings.png](../media/media/travis-ci-settings-repos-coveralls-demo-ruby-settings.png)

---

</details>

Great. [Travis CI](http://travis-ci.org/) is tracking our repo! 

But we're not done yet.

---

</details>

### 2. Add `.travis.yml` to repo

<details>
   <summary><em>How?</em></summary>
   
---

As described in the documentation, our next step is to add a `travis.yml` config file to our repo.<sup>*</sup>

<details>
   <summary>* Where's that documentation?</summary>

---

The free version of Travis CI doesn't offer as much hand-holding as the paid version. Clicking on <strong>Documentation</strong> in the footer even takes us to docs for the paid version of the service, which aren't 100% applicable for the free service.

No matter, though. For us, the [Getting started with GitHub](https://docs.travis-ci.com/user/tutorial/#to-get-started-with-travis-ci-using-github) instructions still apply (after the first three (3) steps aboout adding your repo to Travis CI):

![travis-ci-docs-getting-started-with-github.png](../media/media/travis-ci-docs-getting-started-with-github.png)

According to the instructions, we need to:

<quote> Add a `.travis.yml` file to your repository to tell Travis CI what to do.</quote>

And luckily for us, the example is for Ruby and applies well enough to our project:

![travis-ci-docs-getting-started-with-github-sample-travis-yml.png](../media/media/travis-ci-docs-getting-started-with-github-sample-travis-yml.png)

With the exception that we're not using `jruby`. Instead, we're using "regular ruby", or the MRI (or "Matz") version of Ruby. So our `.travis.yml` looks a little different from the example.

<details>
   <summary>* <em>What if my project's not in Ruby?</em></summary>
   
---

<em>If your project is in a different language, no worries. Travis CI provides a large set of [language-specific guides for forming your `.travis.yml`](https://docs.travis-ci.com/user/language-specific/), [here](https://docs.travis-ci.com/user/language-specific/). For instance, here's the guide for [Javascript with Node](https://docs.travis-ci.com/user/languages/javascript-with-nodejs/).</em>

---

</details>

---

</details>

Our `.travis.yml` will look like this:

```yaml
language: ruby
rvm:
- 2.6.3

branches:
  only:
  - travis
  except:
  - master

script:
  - bundle exec rspec

notifications:
  email: false
```

<details>
   <summary><em>What's all that mean?</em></summary>

---

<em>Break down the config. WIP.</em>

---

</details>

Now that we've composed our `.travis.yml`, the next step is to add it to our project with a new commit:

```
git push
```

If you're committing to a branch on your project, you might want to change the push command to something like:

```
git push -u origin <my-new-branch>
```

But the point is the same, we're adding a new file, `.travis.yml` to our project.

And guess what?

That's all that's required to get Travis Ci to start creating builds of your project.

According to the Travis CI docs:

> *Travis only runs builds on the commits you push after you’ve added a .travis.yml file.*

But, glory is ours now.

Simply go back to [Travis CI (dot org)](https://travis-ci.org/) to see the first build on your project.

For us, that meant going [here](https://travis-ci.org/github/afinetooth/coveralls-demo-ruby). Specifically [https://travis-ci.org/github/afinetooth/coveralls-demo-ruby](https://travis-ci.org/github/afinetooth/coveralls-demo-ruby), where the format of your URL will be:

```
https://travis-ci.org/github/<your-github-username>/<your-github-repo>
```

Your first build will look something like this:

![travis-ci-repo-build-1.png](../media/media/travis-ci-repo-build-1.png)

Simply stated, a successful build; albeit, with not a lot going on.

So we're building at our CI.

Now, let's tell our CI to send its test results to Coveralls.


---

</details>

### 3. Add repo to Coveralls

<details>
   <summary>Do it.</summary>
   
---
   
WIP

---

</details>

### 4. Add `.coveralls.yml` to repo

<details>
   <summary>Do it.</summary>
   
---
   
WIPn

---

</details>

---

```
# To Do:
- [ ] Add Travis logo
- [ ] Add Coveralls logo
```
