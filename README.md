[![Coverage Status](https://coveralls.io/repos/github/afinetooth/coveralls-demo-ruby/badge.svg?branch=travis)](https://coveralls.io/github/afinetooth/coveralls-demo-ruby?branch=travis)

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

This project is configured to send test coverage results to [Coveralls](https://coveralls.io/) through [CircleCI](https://circleci.com/).<sup>*</sup>

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

Fork the [master branch of this project](https://github.com/afinetooth/coveralls-demo-ruby/tree/master) and make your changes to *your fork*.<sup>*</sup>

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

*(Call the new branch whatever you wish, for instance: `circle-ci`.)*

```
git checkout -b circle-ci
```

Great. Now you're in a working branch where you can make changes to your own copy of this repo.

You're ready to continue with this guide.

</details>

---

</details>

After forking the project, keep this window open and refer back to the code in this branch to verify the changes you've made. (Consider it your cheatsheet.)

## Config steps

1. Add repo to [CircleCI](https://circleci.com/)
2. Add `.circleci/config.yml` to repo
3. Add repo to [Coveralls](https://coveralls.io/)
4. Finish [Coveralls](https://coveralls.io/) setup

### 1. Add repo to CircleCI

<details>
   <summary>Do it. </summary>

---

*If you haven't done so already, [fork this project](https://github.com/afinetooth/coveralls-demo-ruby/blob/travis/README.md#how-to-use-this-guide) and clone it down to your local machine so you're working with a local copy that belongs to you.*

*The rest of these steps apply to* <strong>your *project, not this one</strong>.*

---

To add a new public repo to [CircleCI](http://circleci.com/), __[Log in](https://circleci.com/vcs-authorize/)__ at [https://circleci.com/vcs-authorize/](https://circleci.com/vcs-authorize/) with your GitHub login<sup>*</sup>:

![circleci-login.png](../media/media/circleci-login.png)

If you belong to multiple GitHub Organizations, select the one that applies to your project:

![circleci-choose-org.png](../media/media/circleci-choose-org.png)

Then you'll see the list of GitHub projects for your organization:

![circleci-org-projects.png](../media/media/circleci-org-projects.png)

Click __Set Up Project__ next to your newly forked project:

![circleci-setup-project-coveralls-demo-ruby.png](../media/media/circleci-setup-project-coveralls-demo-ruby.png)

Then you'll see the __New Project Set Up__ page for `coveralls-demo-ruby`:

![circleci-project-ready-prompt.png](../media/media/circleci-project-ready-prompt.png)

Here you have the choice to let CircleCI walk you through setting up your project, or add your own config file manually. We're going to add our config file manually because in this context it's actually simpler, and quicker, so...

Click __Add Manually__:

![circleci-start-project-options.png](../media/media/circleci-start-project-options.png)

You'll receive a prompt asking if you've already added a `./circle/config.yml` file to your repo:

![circleci-start-project-add-config-manually.png](../media/media/circleci-start-project-add-config-manually.png)

You haven't, so let's go do that now.

Just leave that window alone.<sup>*</sup> We'll come back to it.

<details>
  <summary>* <em>Oops, what if I clicked <strong>Start Building</strong>?</em></summary>

---

No worries, CircleCI will just try to run your first build...

![circleci-oops-first-build-broken.png](../media/media/circleci-oops-first-build-broken.png)

... and fail, because it couldn't find a `./circle/config.yml` file in your repo.

We'll add that file next, so that problem will soon be rectified.

---

</details>

__Good news, though! [CircleCI](http://circleci.com/) is now tracking your repo.__

---

</details>

### 2. Add `.circleci/config.yml` to repo

<details>
   <summary>Do it. </summary>

---

In your working branch (the one you created when you entered `git checkout -b circle-ci`), create a new, empty file called `.circleci/config.yml`.<sup>*</sup>

<details>
  <summary>* <em>Wait, what does that `.circleci/` part mean?</em></summary>

---

The `.circleci/` part is a folder (an invisible folder), so first just create a new folder and call it `.circleci`. For instance:

```
mkdir .circleci
```

Then open that folder and create the `config.yml` file inside it. For instance:

```
cd .circleci
vi config.yml
```

That's if you want to create a new file in the `vi` editor, via the command line. In most cases, you can simply create a folder and file by the same names in your IDE. Your choice.

Then end result should just be that you have a new folder, and a new file living in that folder, sitting in the root directory of your project:

```
.
..
.circleci/config.yml
lib/
spec/
[...]
```

---

</details>

Now, paste the following configuration settings into your empty `.circleci/config.yml`:

```ruby
version: 2.1

jobs:
  build:
    docker:
      - image: cimg/ruby:2.6.5-node
    steps:
      - checkout
      - run:
          name: Install Bundler
          command: gem install bundler:2.1.4
      - run:
          name: Install dependencies with bundler
          command: bundle install
      - run:
          name: Run tests
          command: bundle exec rspec

workflows:
  version: 2.1
  build_and_test:
    jobs:
      - build:
        filters:
          branches:
            only:
              - circle-ci
```

<details>
  <summary><em>What do those settings mean?</em></summary>

---

__[EXPLAIN CONFIG SETTINGS]__

---

</details>

Save the file and commit it:

```
git add .
git commit -m "Add .circleci/config.yml."
```

Then add the file to your repo by pushing it up to GitHub:

```
git push -u origin circle-ci
```

And guess what?

__That's it! CircleCI is building your project in its remote CI environment.__

<details>
   <summary><em>Prove it!</em></summary>

---

CircleCI started building your project the moment you pushed that last commit:

```
git push -u origin circle-ci
```

To prove that to yourself, just visit [CircleCI](https://app.circleci.com/) to see your first build.

For us, that meant going here:<br />
[https://app.circleci.com/pipelines/github/coverallsapp/coveralls-demo-ruby](https://app.circleci.com/pipelines/github/coverallsapp/coveralls-demo-ruby)

Your URL will be different, but should follow this format:

```
https://app.circleci.com/pipelines/github/<your-github-username>/<your-github-repo>
```

Your first build should look something like this:

![circleci-first-build-success.png](../media/media/circleci-first-build-success.png)

A successful build&mdash;albeit, without much going on.

Notice those test results, which look the same as on our local machine:

```ruby
bundle exec rspec

ClassOne
  covered
    returns 'covered'

Finished in 0.00127 seconds (files took 0.11459 seconds to load)
1 example, 0 failures

Coverage report generated for RSpec to /home/circleci/project/coverage. 4 / 5 LOC (80.0%) covered.
```

That means our tests passed and, therefore, our build succeeded.

</details>

Now, let's tell [CircleCI](https://app.circleci.com/) to start sending its test results to [Coveralls](http://coveralls.io).

---

</details>

### 3. Add repo to Coveralls

<details>
   <summary>Do it. </summary>

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

__Great! [Coveralls](https://coveralls.io/) is now tracking your repo.__

---

</details>

### 4. Finish Coveralls setup

<details>
   <summary>Do it. </summary>

---

[Add content here.]

---

</details>

# Get badged <img src="../media/media/coveralls-badge-80-percent.png" width="99px" height="20px">

<details>
   <summary>Do it. </summary>

---

At the bottom of your Coveralls start page:

__[CHANGE THIS IMAGE TO COVERALLS > CIRCLE-CI BRANCH]__

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

If you've already [configured your project to use Coveralls & CircleCI](https://github.com/afinetooth/coveralls-demo-ruby/blob/circle/README.md#config-steps), then [CircleCI](https://circleci.com/) has already pushed your first build to [Coveralls](https://coveralls.io/), and you've noted that coverage stands at 80%:

__[CHANGE THIS IMAGE TO COVERALLS > CIRCLE-CI BRANCH]__

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

That push will trigger a [new build at CircleCI](#):

__[CHANGE THIS IMAGE TO NEW BUILD AT CIRCLE-CI]__

![travis-new-build-100-percent.png](../media/media/travis-new-build-100-percent.png)

<details>
  <summary><em>Output pertaining to Coveralls:</em></summary>

---

Notice the output spanning from the command running our test suite (`bundle exec rspec`) through the completion of that command (`The command "bundle exec rspec" exited with zero.`), after which we see the completion of the entire build (`Done. Your build exited with zero.`):

__[CHANGE THIS IMAGE TO NEW BUILD DETAILS AT CIRCLE-CI]__

![travis-new-build-100-percent-output.png](../media/media/travis-new-build-100-percent-output.png)

Now notice the very specific output that pertains to our coverage report being sent to Coveralls, which runs from the command (`[Coveralls] Submitting to http://coveralls.io/api/v1`) through (`Coverage report sent to Coveralls.`):

__[CHANGE THIS IMAGE TO NEW BUILD DETAILS AT CIRCLE-CI]__

![travis-new-build-100-percent-output-zoomed.png](../media/media/travis-new-build-100-percent-output-zoomed.png)

---

</details>

Which in turn triggers a [new build at Coveralls](#):

__[CHANGE THIS IMAGE TO COVERALLS > CIRCLE-CI BRANCH]__

![coveralls-new-build-100-percent.png](../media/media/coveralls-new-build-100-percent.png)

Which now reads 100%:

__[CHANGE THIS IMAGE TO COVERALLS > CIRCLE-CI BRANCH]__

![coveralls-new-build-100-percent-zoomed.png](../media/media/coveralls-new-build-100-percent-zoomed.png)

Which is reinforced by your updated badge:

![coveralls-badge-100-percent.png](../media/media/coveralls-badge-100-percent.png)

__Bam! Automated test coverage updates&mdash;from [Coveralls](https://coveralls.io/).__

---

</details>

## More

- [ ] Section: Set up PR Comments - PRs vs pushes, and how to read results.
- [ ] Section: Links to other, more complicated CircleCI scenarios (private repo, parallel builds, etc.)

---

[WIP]

#### Setup Notes / Steps
- [x] Add [`simplecov-lcov`](https://github.com/fortissimo1997/simplecov-lcov) gem and convert test coverage report into lcov format to use coveralls orb
- [x] Add [coveralls orb](https://circleci.com/orbs/registry/orb/coveralls/coveralls)
- [x] Configure orb's upload command with parameters: path_to_lcov & token
- [ ] Embed coverage badge (and probably circleci badge)
- [ ] Write README
