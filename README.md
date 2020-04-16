# coveralls-ruby-demo

[Coveralls](http://coveralls.io) demo project, using:

* Language: [Ruby](https://www.ruby-lang.org/) 
* Test Suite(s): [Rspec](https://rspec.info/) 
* Code Coverage Library: [Simplecov](https://github.com/colszowka/simplecov)
* SCM Service: [GitHub](https://github.com/)

### How to run it:

```
bundle install
bundle exec rspec
```

## About Coveralls

[Coveralls](http://coveralls.io) is a web service that sends code coverage reports to a shared workspace so you and your team can track your projects' code coverage over time. [Coveralls](http://coveralls.io) is language- and CI-agnostic, but it lets you control whether your builds pass or fail based on code coverage metrics that you set.

## How It Works

Before your project gets to [Coveralls](http://coveralls.io), it must already be using a code coverage library to generate coverage results (in this project, that's [Simplecov](https://github.com/colszowka/simplecov)). Your CI will run your tests, and your code coverage library, then post the results to [Coveralls](http://coveralls.io).

```
<how it works diagram>
```

We'll set up this project to do exactly that, with these five (5) steps:

## Next Steps

1. Understand test coverage in this project
2. Run tests for the first time
3. Add tests and see coverage change
4. Configure this project to use Coveralls
5. Verify expected code coverage with Coveralls

## 1. Understand test coverage in this project

Before we start sending coverage results to [Coveralls](http://coveralls.io), let's first understand the nature the test coverage in this demo project.

This is the totality of the code in this project:

```ruby
class ClassOne

  def self.covered
    "covered"
  end

  def self.uncovered
    "uncovered"
  end

end
```

And these are the tests:

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

Notice that right now, only one of the two methods in `ClassOne` is being tested.

## 2. Run tests for the first time

Let's run the test suite for the first time and see what the results are.

If you haven't already, go ahead and clone the project down to your local machine:

```
git clone git@github.com:afinetooth/coveralls-demo-ruby.git
```

Now, `cd` into `coveralls-demo-ruby` and run this command to install the dependencies:

```
bundle install
```

Finally, run the test suite, [Rspec](https://rspec.info/).

```
bundle exec rspec
```

You'll notice test results on the screen, which should look like this:

```ruby
<test results>
```

In additional to the test results themselves, we have the added benefit of test _coverage_ results, from using our test coverage library, [Simplecov](https://github.com/colszowka/simplecov). 

Every time we run our test suite, [Simplecov](https://github.com/colszowka/simplecov), in the background, generates HTML-based code coverage results, which you can see by opening the newly created file at `/coverage/index.html` in your browser, or by issuing this command in your terminal:

```
open coverage/index.html
```

The first results should look like this:

![80% Coverage - Index View](../media/media/coverage_80_percent_index.png)

Where coverage stands at 80% for the entire project.

Clicking on `lib/class_one.rb` brings up results for the file:

![80% Coverage - File View](../media/media/coverage_80_percent_file.png?raw=true)

Where you'll notice covered lines in green, and uncovered lines in red.

One might expect the coverage results here to be 50%, given that `ClassOne` has two (2) methods (`covered` and `uncovered`) and we're only testing one of them. However, that's not how it works. Instead, Simplecov counts *relevant lines* in each file and compares the number of covered lines to uncovered lines to determine the file's coverage percentage. 

In our case, 4/5 lines are covered, indicating 80% coverage.

## 3. Add tests and see coverage change

Now let's add more tests and see how coverage changes. 

To "add" tests, we'll simply un-comment the test of the second method in `ClassOne`:

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

Now run the test suite again:

```
bundle exec rspec
```

And open the new results at `coverage/index.html`.

Here's how things look now:

![100% Coverage - Index View](../media/media/coverage_100_percent_index.png?raw=true)

Notice coverage has increased from 80% to 100% (and turned green).

And now, if we click on `lib/class_one.rb` we see:

![100% Coverage - File View](../media/media/coverage_100_percent_file.png?raw=true)

Five (5) out of five (5) relevant lines are now covered, resulting in 100% coverage for the file, which means 100% coverage for our one-file project.

## 4. Configure this project to use Coveralls

Now that you understand how code coverage works in this project, we're in a good place to take the next step, configuring the project to send test coverage results to [Coveralls](http://coveralls.io).

Once we do that, we'll be able to verify our same expectations, but this time through Coveralls; first, 80% coverage, and then, 100% coverage.
 
Now's a good time to understand the next factor that affects how you'll want to configure your project: __CI Service__

### Which CI Service will you use?

[Explain CI & CI Services for beginners]

WIP


