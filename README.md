# coveralls-ruby-demo

Coveralls demo project, using:

* Language: [Ruby](https://www.ruby-lang.org/) 
* Test Suite(s): [Rspec](https://rspec.info/) 
* Code Coverage Library: [Simplecov](https://github.com/colszowka/simplecov)

### How to run it:

```
bundle install
bundle exec rspec
```

### Test coverage

This is the totality of the code in this project:

```
Code here.
```

And these are the tests:

```
Code here.
```

Notice that right now, only one of the methods in `ClassOne` are being tested.

### Running tests for the first time

Let's run the test suite for the first time and see what the results are:

```
bundle exec rspec
```

The command `bundle exec rspec` runs the [Rspec](https://rspec.info/) test suite, upon which [Simplecov](https://github.com/colszowka/simplecov) generates HTML-based code coverage results, which you can see by opening the newly created file at `/coverage/index.html` in your browser.

The first results should look like this:

![alt text](../media/coverage_80_percent_index.png?raw=true)

Where coverage stands at 80% for one file, `lib/class_one.rb`.

Clicking on `lib/class_one.rb` brings up results for the file:

![alt text](../media/coverage_80_percent_file.png?raw=true)

Where you'll notice covered lines in green, and uncovered lines in red.

One might expect the coverage results here to be 50%, since `ClassOne` has two (2) methods, where one method is covered by tests (`covered`) and the other method (`uncovered`) is not. However, that's not how it works. Instead, Simplecov counts relevant lines in each file and compares the number of covered to uncovered lines to determine it's coverage percentage. In our case, 4/5 lines are covered, indicating 80% coverage.

### Add tests and see coverage change

Now let's add some tests and see how coverage changes. 

To add tests, we're simply going to un-comment the test of the second method in `spec/class_one_spec.rb`:

```
Code here.
```

Then we'll run the test suite again:

```
bundle exec rspec
```

Then, let's open up the HTML-based results at `coverage/index.html`.

Here's how they look now:

![alt text](../media/coverage_100_percent_index.png?raw=true)

Notice coverage has increased from 80% to 100% (and turned green).

And now, if we click on `lib/class_one.rb` we'll see:

![alt text](../media/coverage_100_percent_file.png?raw=true)

Five (5) out of five (5) relvant lines are now covered, resulting in 100% coverage for the file, and 100% coverage for our one-file project.
