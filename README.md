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

The command `bundle exec rspec` runs the [Rspec](https://rspec.info/) test suite, upon which [Simplecov](https://github.com/colszowka/simplecov) generates HTML-based code coverage results, which you can see by loading the newly created `/coverage/index.html` in your browser.

#### First pass

The first results should look like this:

[IMAGE]

Where coverage stands at 80% for the one file, `lib/class_one.rb`.

Clicking on the filename, `lib/class_one.rb` brings up results for the file:

[IMAGE]

Where you'll notice covered lines in green, and uncoverd lines in red.

One might expect the coverage results to be 50%, since `ClassOne` has two (2) methods, where one method is covered (`coevred`) and the other is not (`uncoevred`). However, that's not how it works. Instead Simplecov simple counts relevant lines and compares the number of covered to uncovered lines to determine it's coverage percentage. In our case, 4/5 lines are covered, indicating 80% coverage.

#### Second pass
WIP
