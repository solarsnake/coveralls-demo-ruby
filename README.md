[![Coverage Status](https://coveralls.io/repos/github/afinetooth/coveralls-demo-ruby/badge.svg?branch=travis)](https://coveralls.io/github/afinetooth/coveralls-demo-ruby?branch=travis)

# coveralls-ruby-demo for Travis CI

[Coveralls](https://coveralls.io/) demo project, using:

* [Ruby](https://www.ruby-lang.org/) — *Language*
* [Rspec](https://rspec.info/) — *Testing Library*
* [Simplecov](https://github.com/colszowka/simplecov) — *Code Coverage Library*

And these services:

* [Travis CI](http:://travis-ci.org) — *CI Service*
* [Coveralls](https://coveralls.io/) — *Test Coverage Service*

# Welcome

If you've gotten this far, we can assume:

<dl>
  <dt>1. You understand <a href="https://github.com/afinetooth/coveralls-demo-ruby#1-understand-test-coverage-in-this-project">how test coverage works in this project</a>.</dt>
  <dd>If not, start back at the <a href="https://github.com/afinetooth/coveralls-demo-ruby">master README</a>.</dd>

  <dt>2. You've chosen <a href="https://travis-ci.org/">Travis CI</a> as your CI Service.</dt>
  <dd>If not, head back to the <a href="https://github.com/afinetooth/coveralls-demo-ruby">master README</a> and <a href="https://github.com/afinetooth/coveralls-demo-ruby#which-ci-service-will-you-use">choose a different CI / branch</a>.</dd>
</dl>

# Configure your project for Coveralls & Travis CI

This project is configured to send test coverage results to [Coveralls](https://coveralls.io/) through [Travis CI](https://travis-ci.org/).<sup>*</sup>

<details>
   <summary>* <em>How do we know it's working?</em></summary>

---

Notice the Coveralls badge at the top of the page:

[![Coverage Status](https://coveralls.io/repos/github/afinetooth/coveralls-demo-ruby/badge.svg?branch=travis)](https://coveralls.io/github/afinetooth/coveralls-demo-ruby?branch=travis)

That tells us we're configured correctly and successfully receiving coverage reports back from [Coveralls](https://coveralls.io/).

---

</details>

This guide will walk you through the configuration process.

## How to use this guide

Fork the [master branch](https://github.com/afinetooth/coveralls-demo-ruby/tree/master) of this project and make your changes to *your fork*.<sup>*</sup>

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
4. Finish `coveralls` setup

### 1. Add repo to Travis CI

<details>
   <summary><em>Do it.</em></summary>

---

*If you haven't done so already, [fork this project](https://github.com/afinetooth/coveralls-demo-ruby/blob/travis/README.md#how-to-use-this-guide) and clone it down to your local machine so you're working with a local copy that belongs to you.*

*The rest of these steps apply to* <strong>your *project, not this one</strong>.*

---

To add a new public repo to Travis, __[Sign in](https://travis-ci.org/signin)__ at [http://travis-ci.org/](http://travis-ci.org/) with your GitHub login<sup>*</sup>:

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

To add your repo to Travis, simply click the toggle control next to your __repo name__, setting it to __ON__:

![travis-ci-settings-repos-coveralls-demo-ruby.png](../media/media/travis-ci-settings-repos-coveralls-demo-ruby.png)

<details>
   <summary><em>What about those settings?</em></summary>

---

<em>Not necessary right now. You can click on the <strong>Settings button</strong> next to your repo to see some basic configuration options, but for now let's leave everything there as-is.</em>

<em>Our looks like this:</em>

![travis-ci-settings-repos-coveralls-demo-ruby-settings.png](../media/media/travis-ci-settings-repos-coveralls-demo-ruby-settings.png)

---

</details>

__Great! [Travis](http://travis-ci.org/) is now tracking your repo.__

---

</details>

### 2. Add `.travis.yml` to repo

<details>
   <summary><em>Do it.</em></summary>

---

According to the <a href="https://docs.travis-ci.com/user/tutorial/">documentation</a>,<sup>*</sup> our next step is to add a `.travis.yml` config file to our repo.

<details>
   <summary>* <em>Where's that documentation?</em></summary>

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

Here's the version to use for your project:

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
   <summary><em>What do those settings mean?</em></summary>

---

Pretty straighforward:

```
language: ruby
rvm:
- 2.6.3
```

Tells Travis that our project is in `ruby`, specifically, version `2.6.3`.

(Moreover, we're using the default Ruby interpreter&mdash;MRI, or "Matz Ruby." If we were using a different interpreter, such as JRuby, then we'd need another line below `-2.6.3`, specifically `- jruby` (*same level of indentation*)).

```
script:
  - bundle exec rspec
```

Is telling Travis how to run our project.

In this case, we're asking Travis to run our test suite (RSpec).

Finally:

```
notifications:
  email: false
```

Tell Travis "don't send me an email every time I push a commit." Completely optional, just a suggestion to keep your first builds from being too noisy.

If you'd like to see how those emails look, just replace `false` with your email, like:

```
notifications:
  email: afinetooth@gmail.com
```

And that's it. Pretty simple, right?

<details>
   <summary><em>Hey, why is my `.travis.yml` different from the version in this branch?</em></summary>

---

Your version is simpler than ours for one reason.

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

Where the difference is this section:

```yaml
branches:
  only:
  - travis
  except:
  - master
```

That `branches:` section just means we're doing something a little fancier around our branches compared to your project.

Specifically, in our project we only want to run builds on pushes to our `travis` branch, which is the only branch we've configured to work with Travis CI. (Other branches work with other CI services.)

Therefore, we use the `only:` declaration and specify `travis` (*for the `travis` branch*).

For good measure, we've also added the `except:` declaration&mdash;not strictly necessary, but informative in that we never want to to run builds on commits to our `master` branch. That's because our master branch is meant to remain a pristine area of unconfigured demo code. (Code that will run nowhere except on our local machine.)

By contrast, your first Travis config can be more "plain vanilla," permitting builds on any branch you might create on your project.

Thus, no need for you to declare anything under `branches:`.

</details>

---

</details>

Just paste those contents into a new, empty file in your IDE titled `.travis.yml`.

Then commit it:

```
git add .
git commit -m "Add .travis.yml."
```

Then add the file to your repo by pushing it up to GitHub:

```
git push -u origin <my-new-branch>
```

And guess what?

__That's it! Travis is building your project in a remote CI environment.__

<details>
   <summary><em>Prove it!</em></summary>

---

Travis started your first build the moment you pushed your last commit:

```
git push -u origin <my-new-branch>
```

To prove that to yourself, just visit [Travis](https://travis-ci.org/) to see your first build.

For us, that meant going here:<br />
[https://travis-ci.org/github/afinetooth/coveralls-demo-ruby](https://travis-ci.org/github/afinetooth/coveralls-demo-ruby)

Your URL will be different, but should follow this format:

```
https://travis-ci.org/github/<your-github-username>/<your-github-repo>
```

Your first build should look something like this:

![travis-ci-first-build.png](../media/media/travis-ci-first-build.png)

Simply stated, a successful build&mdash;albeit, without much going on.

Notice those test results, which look the same as on our local machine:

```
$ bundle exec rspec

ClassOne
  covered
    returns 'covered'

Finished in 0.00176 seconds (files took 0.13071 seconds to load)
1 example, 0 failures

Coverage report generated for RSpec to /home/travis/build/afinetooth/coveralls-demo-ruby/coverage. 4 / 5 LOC (80.0%) covered.
The command "bundle exec rspec" exited with 0.
```

That means our tests passed and therefore our build succeeded.

</details>

Now, let's tell Travis to start sending its test results to Coveralls.

---

</details>

### 3. Add repo to Coveralls

<details>
   <summary>Do it.</summary>

---

To add your repo to [Coveralls](https://coveralls.io/sign-in), go to [http://coveralls.io/sign-in](https://coveralls.io/sign-in) and __Sign In__ with GitHub:

![coveralls-sign-in.png](../media/media/coveralls-sign-in.png)

Upon first sign-in, you won't have any active repos, so go to [Add Repos](https://coveralls.io/repos/new) and find a list of your public repos:

![coveralls-add-repo.png](../media/media/coveralls-add-repo.png)

To add your repo, simply click the __Toggle control__ next to your __repo name__, switching it to __ON__:

![coveralls-add-repo-turn-on.png](../media/media/coveralls-add-repo-turn-on.png)

<details>
   <summary><em>Wait, I don't see my repo!</em></summary>

---

In that case, click on the __Sync Repos button__ in the upper right:

![coveralls-add-repo-sync-repos.png](../media/media/coveralls-add-repo-sync-repos.png)

<details>
   <summary><em>What about my private repos?</em></summary>

---

[Coveralls](https://coveralls.io/) is free to use for public repos. To add private repos, you'll need to [subscribe](http://coveralls.io/sign-up).

</details>

---

</details>

Great! [Coveralls](https://coveralls.io/) is now tracking your repo.

---

</details>

### 4. Finish `coveralls` setup

<details>
   <summary>Do it.</summary>

---

[Coveralls](https://coveralls.io/) provides easy-to-follow setup instructions for each new repo.

To access them, just click the __Details button__ next to your repo name:

![coveralls-add-repo-turn-on.png](../media/media/coveralls-add-repo-turn-on.png)

And follow the steps presented:

![coveralls-new-repo-setup.png](../media/media/coveralls-new-repo-setup.png)

Our first step is technically optional, but in the interest of good form let's add a new file called `.coveralls.yml` to our repo with the following contents:

```yaml
service-name: travis-ci
```

<details>
   <summary><em>Why is this optional?</em></summary>

---

Adding a `.coveralls.yml` is technically optional for [Coveralls](https://coveralls.io/) because [Travis CI](http://travis-ci.org/) is Coveralls' default CI service. Coveralls was originally created for use with [Travis CI (dot org)](http://travis-ci.org/) and has since grown to support more Ci services.

---

</details>

*We don't need to add a `repo-token` to our `.coveralls.yml` file at this time, so we can skip that part.*

Next step, add the `coveralls` gem to our Gemfile:

```ruby
gem 'coveralls', require: false
```

And for good measure, since there's currently a conflict between the `coveralls` gem and the latest version of `simplecov`, let's lock down the version of `simplecov` we'll use in our project. In your Gemfile, add this line *above* the line, `gem 'coveralls', require: false` so the last two lines of our Gemfile look like this:

```ruby
gem 'simplecov', '0.16'
gem 'coveralls', require: false
```

Since we're changing the version of our `simplecov` gem, we need to update the gems in our project with this command:

```
bundle install
```

Last step, let's add a line of code that invokes `coveralls` to the very top of our test suite's helper file. For our test suite, [RSpec](http://rspec.info), that's `spec_helper.rb`:

```ruby
require 'coveralls'
Coveralls.wear!

# Your code here
```

Save the file.

Commit your changes:

```
git add .
git commit -m "Add coveralls gem and .coveralls.yml."
```

Push them up to GitHub:

```
git push
```

And that's it!

Coverage for your next Travis build will now appear on the details page for your repo, in place of the instructions we just followed.

Your URL for that page will have the format:

```
https://coveralls.io/github/<your-github-username>/<your-github-repo-name>
```

Your first code coverage report will look something like this:

![coveralls-first-coverage-report.png](../media/media/coveralls-first-coverage-report.png)

Congratulations, you're sending code coverage results to [Coveralls](https://coveralls.io/).

---

</details>

# Get badged <img src="../media/media/coveralls-badge-80-percent.png" width="99px" height="20px">

<details>
   <summary>Do it.</summary>

---

At the bottom of your Coveralls start page:

![coveralls-first-coverage-report.png](../media/media/coveralls-first-coverage-report.png)

You'll see a box like this instructing you to badge your repo:

![coveralls-badge-your-repo.png](../media/media/coveralls-badge-your-repo.png)

Click the __Embed button__ and choose the version of markup that applies for you:

![coveralls-badge-your-repo-choose-embed-markup.png](../media/media/coveralls-badge-your-repo-choose-embed-markup.png)

*(For a GitHub README, that's the __Markdown__ version.)*

Then paste the markup into the top of your README, and...

__Voilà__:

![coveralls-badge-80-percent.png](../media/media/coveralls-badge-80-percent.png)

__Your repo is badged!__

---

</details>

# Verify changes in test coverage via Coveralls <img src="../media/media/coveralls-badge-100-percent.png" width="106px" height="20px">

<details>
   <summary>Do it. </summary>

---

Since you understand [how test coverage works in this project](https://github.com/afinetooth/coveralls-demo-ruby#1-understand-test-coverage-in-this-project), let's verify those same results through the [Coveralls](https://coveralls.io/) service.

If you've already [configured your project to use Coveralls & Travis CI](https://github.com/afinetooth/coveralls-demo-ruby/blob/travis/README.md#config-steps), then [Travis CI](https://travis-ci.org/) has already pushed your first build to [Coveralls](https://coveralls.io/), and you've noted that coverage stands at 80%:

![coveralls-first-build-80-percent.png](../media/media/coveralls-first-build-80-percent.png)

The badge on your repo reinforces that:

![coveralls-badge-80-percent.png](../media/media/coveralls-badge-80-percent.png)

Now let's validate that [Coveralls](https://coveralls.io/) is tracking *changes in test coverage* on our project.

To do that, let's add a test that lifts coverage to 100%.

Open the test file, `/spec/class_one_spec.rb`, and uncomment the second test in the file, so that this:

```ruby
require 'spec_helper'
require 'class_one'

describe ClassOne do

  describe "covered" do
    it "returns 'covered'" do
      expect(ClassOne.covered).to eql("covered")
    end
  end

  # Uncomment below to achieve 100% coverage
  # describe "uncovered" do
  #   it "returns 'uncovered'" do
  #     expect(ClassOne.uncovered).to eql("uncovered")
  #   end
  # end
end
```

Becomes this:

```ruby
require 'spec_helper'
require 'class_one'

describe ClassOne do

  describe "covered" do
    it "returns 'covered'" do
      expect(ClassOne.covered).to eql("covered")
    end
  end

  # Uncomment below to achieve 100% coverage
  describe "uncovered" do
    it "returns 'uncovered'" do
      expect(ClassOne.uncovered).to eql("uncovered")
    end
  end
end
```

Now, save the file, commit the change and push it to GitHub:

```
git commit -m "Add tests to make coverage 100%."
git push
```

That push will trigger a [new build at Travis CI](#):

![travis-new-build-100-percent.png](../media/media/travis-new-build-100-percent.png)

<details>
  <summary><em>Output pertaining to Coveralls:</em></summary>

---

Notice all the output spanning from the command running our test suite (`bundle exec rspec`) through the completion of that command (`The command "bundle exec rspec" exited with zero`), after which we see the completion of the entire build (`Done. Your build exited with zero`):

![travis-new-build-100-percent-output.png](../media/media/travis-new-build-100-percent-output.png)

The very specific output that pertains to sending our coverage report to Coveralls is as follows, and runs from the command (`ccc`) through (`nnn`):

![travis-new-build-100-percent-output-zoomed.png](../media/media/travis-new-build-100-percent-output-zoomed.png)

---

</details>

Which in turn triggers a [new build at Coveralls](#):

![coveralls-new-build-100-percent.png](../media/media/coveralls-new-build-100-percent.png)

Which now reads 100%:

![coveralls-new-build-100-percent-zoomed.png](../media/media/coveralls-new-build-100-percent-zoomed.png)

Which is reinforced by your updated badge:

![coveralls-badge-100-percent.png](../media/media/coveralls-badge-100-percent.png)

__Bam! Automated test coverage updates&mdash;from [Coveralls](https://coveralls.io/).__

---

</details>

# More

- [ ] Section: Set up PR Comments - PRs vs pushes, and how to read results.
- [ ] Section: Links to other, more complicated Travis CI scenarios (parallel builds, etc.)
