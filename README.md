[![Coverage Status](https://coveralls.io/repos/github/afinetooth/coveralls-demo-ruby/badge.svg?branch=travis)](https://coveralls.io/github/afinetooth/coveralls-demo-ruby?branch=travis)

# coveralls-ruby-demo for Travis CI

[Coveralls](https://coveralls.io/) demo project, using:

* [Ruby](https://www.ruby-lang.org/) — *Language*
* [Rspec](https://rspec.info/) — *Testing Library*
* [Simplecov](https://github.com/colszowka/simplecov) — *Code Coverage Library*

And the services:

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

# Coveralls & Travis CI

This project is configured to send test coverage results to [Coveralls](https://coveralls.io/) through [Travis CI](https://travis-ci.org/).<sup>*</sup>

<details>
   <summary>* <em>How do we know?</em></summary>

---

Notice the Coveralls badge at the top of the page:

[![Coverage Status](https://coveralls.io/repos/github/afinetooth/coveralls-demo-ruby/badge.svg?branch=travis)](https://coveralls.io/github/afinetooth/coveralls-demo-ruby?branch=travis)

That tells us we're configured correctly and successfully receiving coverage reports back from [Coveralls](https://coveralls.io/).

---

</details>

This guide will walk you through the configuration process.

## How to use this guide

Fork the [master branch](https://github.com/afinetooth/coveralls-demo-ruby/tree/master) of this project and make your changes to it.<sup>*</sup> 

<details>
   <summary>* <em>How do I do that?</em></summary>
   
---

<details>
   <summary><strong>1. Fork the project</strong></summary>

---

Click the __Fork__ button:

![fork-this-project.png](../media/media/fork-this-project.png)

GitHub will tell you it's working on your fork:

![forking-this-project.png](../media/media/forking-this-project.png)

When it's done, you'll see a new repo that looks just like the original, called `coveralls-demo-ruby`, only now you'll notice it belongs to you:

![you-forked-this-project.png](../media/media/you-forked-this-project.png)

---

</details>

<details>
   <summary><strong>2. Clone the project</strong></summary>

---


Click the __Clone or download__ button, then click the __Clipboard icon__ to copy the URL:

![clone-this-project.png](../media/media/clone-this-project.png)

Now go to your terminal and enter the clone command:

```
git clone git@github.com:<your-github-username>/coveralls-demo-ruby.git
```

Your results should look something like this:

```
Cloning into 'coveralls-demo-ruby'...
Enter passphrase for key '/Users/jameskessler/.ssh/id_rsa': 
remote: Enumerating objects: 66, done.
remote: Counting objects: 100% (66/66), done.
remote: Compressing objects: 100% (66/66), done.
remote: Total 543 (delta 40), reused 0 (delta 0), pack-reused 477
Receiving objects: 100% (543/543), 2.51 MiB | 3.05 MiB/s, done.
Resolving deltas: 100% (335/335), done.
```

Great. Now you have a working copy of the project on your local machine.

---

</details>

<details>
   <summary><strong>3. Create a new working branch</strong></summary>

---

Change directories into the project directory:

```
cd coveralls-demo-ruby/
```

And create the new working branch:

*(Call the new branch whatever you wish, for instance: `travis-ci`.)*

```
git checkout -b travis-ci
```

Great. Now you're in a working branch where you can make changes to your own copy of this repo.

You're ready to continue with this guide.

</details>

---

</details>

After forking the project, keep this window open and refer back to the code in this branch to verify the changes you've made. (Consider it your cheatsheet.)

## Config steps

1. Add repo to [Travis CI](https://travis-ci.org/)
2. Add `.travis.yml` to repo
3. Add repo to [Coveralls](https://coveralls.io/)
4. Add `.coveralls.yml` to repo

### 1. Add repo to Travis CI

<details>
   <summary><em>Do it.</em></summary>
   
---
   
*If you haven't done so already, [fork this project](https://github.com/afinetooth/coveralls-demo-ruby/blob/travis/README.md#how-to-use-this-guide) and clone it down to your local machine so you're working with a local copy that belongs to you.*

*The rest of these steps apply to* <strong>your *project, not this one</strong>.*

---

To add a public repo to Travis, __[Sign in](https://travis-ci.org/signin)__ at [http://travis-ci.org/](http://travis-ci.org/) with your GitHub login<sup>*</sup>:

![travis-ci-sign-in.png](../media/media/travis-ci-sign-in.png)

<details>
   <summary>* <em>Need to sign up?</em></summary>

---

Just click <strong><a target="_blank" href="https://travis-ci.org/signup">Sign up</a></strong> and use your GitHub login:

![travis-ci-sign-up.png](../media/media/travis-ci-sign-up.png)

---
</details>

Once you're signed in, click on your profile image on the uppper right and choose <strong>Settings</strong>, or go directly to:<br />
[https://travis-ci.org/account/repositories](https://travis-ci.org/account/repositories):

![travis-ci-settings-repos.png](../media/media/travis-ci-settings-repos.png)

<details>
   <summary><em>Wait! I don't see my repo!</em></summary>
   
---

If Travis doesn't already list all of your *public repos*, click the __Sync account__ button to refresh the list.<sup>*</sup>

<details>
   <summary>* <em>What about private repos?</em></summary>

---

<em><a href="http://travis-ci.org/">http://travis-ci.org/</a> is the free version of the Travis CI service that's always free for public repos. To manage private repos, you'll want to join the paid service at <a href="http://travis-ci.com/">http://travis-ci.com/</a>.</em>

</details>

---

</details>

To add your repo to Travis, simply click the toggle control next to your repo, setting it to __ON__:

![travis-ci-settings-repos-coveralls-demo-ruby.png](../media/media/travis-ci-settings-repos-coveralls-demo-ruby.png)

<details>
   <summary><em>What about those settings?</em></summary>

---

<em>Not necessary right now. You can click on the <strong>Settings button</strong> next to your repo to see some basic configuration options, but for now let's leave everything there as-is.</em>

<em>Our looks like this:</em>

![travis-ci-settings-repos-coveralls-demo-ruby-settings.png](../media/media/travis-ci-settings-repos-coveralls-demo-ruby-settings.png)

---

</details>

__Great! [Travis](http://travis-ci.org/) is tracking your repo.__ 

*Next step...*

---

</details>

### 2. Add `.travis.yml` to repo

<details>
   <summary><em>Do it.</em></summary>
   
---

As described in the <a href="https://docs.travis-ci.com/user/tutorial/">documentation</a><sup>*</sup>, our next step is to add a `travis.yml` config file to our repo.

<details>
   <summary>* <em>Where'd you find that documentation?</em></summary>

---

<em>The free version of Travis CI doesn't offer as much hand-holding as the paid version. Clicking on <strong>Documentation</strong> in the footer even takes us to docs for the paid version of the service, which aren't 100% applicable for the free service.</em>

No matter, though. For us, the [Getting started with GitHub](https://docs.travis-ci.com/user/tutorial/#to-get-started-with-travis-ci-using-github) instructions still apply&mdash;<em>after the first three (3) steps aboout adding your repo to travis-ci.com</em>:

![travis-ci-docs-getting-started-with-github.png](../media/media/travis-ci-docs-getting-started-with-github.png)

That `.travis.yml` is for Ruby and applies well <em>enough</em> to our project...

![travis-ci-docs-getting-started-with-github-sample-travis-yml.png](../media/media/travis-ci-docs-getting-started-with-github-sample-travis-yml.png)

...with the exception that we're not using `jruby`. Instead, we're using "regular old ruby", or the MRI (or "Matz") version of Ruby, so our `.travis.yml` looks a little different from the example.

<details>
   <summary>* <em>What if my project's not in Ruby?</em></summary>
   
---

<em>If your project is in a different language, no worries. Travis CI provides a set of [language-specific guides](https://docs.travis-ci.com/user/language-specific/) for forming your `.travis.yml`. For instance, here's the guide for [Javascript with Node](https://docs.travis-ci.com/user/languages/javascript-with-nodejs/).</em>

<em>For this project we're using Ruby, so go with the Ruby config for now.</em>

</details>

---

</details>

Our `.travis.yml` looks like this:

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
   <summary><em>What do those settings mean?</em></summary>

---

<em>Break down the config settings. WIP.</em>

---

</details>

Here's the version you'll want to use for your project:

```yaml
language: ruby
rvm:
- 2.6.3

script:
  - bundle exec rspec

notifications:
  email: false
```

<details>
   <summary><em>Why the difference?</em></summary>

---

<em>Explain why the differences in config settings. WIP.</em>

---

</details>

Just paste that into a new, empty file in your IDE named `.travis.yml`.

Now, the last step is to add that file to your repo by committing it.

Maybe something like:

```
git push -u origin <my-new-branch>
```

And guess what? 

__That's it!__

That's all that's required to get Travis CI to start building your project in its virtual environments.

To prove it to yourself, go back to [Travis](https://travis-ci.org/) to see the first build on your project.

For us, that meant going here:<br />
[https://travis-ci.org/github/afinetooth/coveralls-demo-ruby](https://travis-ci.org/github/afinetooth/coveralls-demo-ruby) 

Your URL will be:

```
https://travis-ci.org/github/<your-github-username>/<your-github-repo>
```

And your first build will look something like this:

![travis-ci-repo-build-1.png](../media/media/travis-ci-repo-build-1.png)

Simply stated, a successful build; albeit, without a lot going on.

__We're building at our CI!__

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
