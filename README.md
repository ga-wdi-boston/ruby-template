[![General Assembly Logo](https://camo.githubusercontent.com/1a91b05b8f4d44b5bbfb83abac2b0996d8e26c92/687474703a2f2f692e696d6775722e636f6d2f6b6538555354712e706e67)](https://generalassemb.ly/education/web-development-immersive)

# ruby-template

## Updating Dependencies

At the beginning of each cohort:

-   Update ruby verison in [`.ruby-version`](.ruby-version)
-   Update [`Gemfile`](Gemfile):
    -   Update ruby version.
    -   Find updated versions of gems referenced from Gemfile.
    -   Update semantic versions in Gemfile as appropriate.
-   `bundle update`
-   `bin/rake # runs both nag and test`

Fix errors and conflicts as necessary.

## Structure

Dependencies are stored in [`Gemfile`](Gemfile).

Do not configure `bin/rake` tasks directly in [`Rakefile`](Rakefile). Instead,
store tasks in the [`lib/tasks`](lib/tasks) directory.  Task aliases should go
in [`lib/tasks/aliases.rake`](lib/tasks/aliases.rake).

Developers should store ruby files in [`lib`](lib), or perhaps a subdirectory.
If a command line script is needed, it should go in [`bin`](bin).

## Code blocks

With this in the markdown:

&lt;!-- start code block file="lib/example.rb" --&gt;

This gets replaced with the contents of `lib/example.rb`

&lt;!-- end code block --&gt;

running:

```sh
cp README.md README.bak
bin/add-code-block.rb README.bak >README.md
```

produces:

<!-- start code block file="lib/example.rb" -->
```rb
# frozen_string_literal: true

# An example class
class Example
  attr_accessor :value
  def initialize(value = 0)
    @value = value
  end
end
```
<!-- end code block -->

Check the markdown source to see what happens.

## Tasks

Developers should run these often!

-   `bin/rake nag`  (or `bundle exec rake nag`):
    runs code quality analysis tools on your code and complains.
-   `bin/rake test` (or `bundle exec rake test`): runs automated tests.
-   `bin/rake` will run both `nag` and `test`

## [License](LICENSE)

1.  All content is licensed under a CC­BY­NC­SA 4.0 license.
1.  All software code is licensed under GNU GPLv3. For commercial use or
    alternative licensing, please contact legal@ga.co.
