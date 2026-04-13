# Teaching: Gems and Bundler

## Context
The student has Ruby installed and working. They have used npm (from the Node module) so they understand the concept of language-level package managers. Now they will learn Ruby's equivalent: gems and Bundler. Draw parallels to npm throughout.

## The challenge
Install a gem directly, then set up a project with a Gemfile and use Bundler to manage dependencies.

## Your approach
1. Draw the parallel immediately:
   - npm = gem (the command to install packages)
   - package.json = Gemfile (the file listing dependencies)
   - node_modules = vendor/bundle (where packages get stored)
   - npm install = bundle install (install all dependencies)
2. Install a gem directly: `gem install colorize` (a simple gem that adds color to terminal output).
3. Test it:
   ```ruby
   ruby -e 'require "colorize"; puts "This is red".red; puts "This is blue".blue'
   ```
4. Now show the Bundler workflow:
   - Create a project directory: `mkdir ~/ruby-test && cd ~/ruby-test`
   - Create a Gemfile manually (teach them the format):
     ```ruby
     source "https://rubygems.org"
     gem "colorize"
     gem "faker"
     ```
   - Run `bundle install`
   - Show them the generated `Gemfile.lock` and explain it pins exact versions
5. Create a small Ruby script that uses both gems:
   ```ruby
   require 'bundler/setup'
   require 'colorize'
   require 'faker'
   puts Faker::Name.name.green
   ```
6. Run it with `ruby script.rb`.

## Prompting coaching
- Encourage comparison: "How is this similar to npm? How is it different?"
- Teach: "What questions should I ask before adding a dependency to my project?"
- Model: "What does Gemfile.lock do and why should I commit it to git?"

## Quiz questions
- What is the equivalent of `npm install express` in Ruby?
- What is the purpose of `Gemfile.lock`?
- Why would you use Bundler instead of just `gem install`?
- What does `require 'bundler/setup'` do at the top of a Ruby file?

## Hints (only if stuck)
1. If `bundle` is not found, install it: `gem install bundler`.
2. The Gemfile must have `source "https://rubygems.org"` at the top.
3. After `bundle install`, run scripts with `bundle exec ruby script.rb` if regular `ruby` does not find the gems.
