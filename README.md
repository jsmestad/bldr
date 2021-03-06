[![Build Status](http://travis-ci.org/ajsharp/bldr.png)](http://travis-ci.org/ajsharp/bldr)


# Bldr

Bldr is a minimalist templating library that provides a simple DSL for generating
json documents from ruby objects. It currently supports Sinatra out of
the box -- Rails 3 support is planned for the near future.

If you would like to contribute, pull requests with specs are warmly accepted :)

## Why

If you're building an API, `Model#to_json` just doesn't cut it. Besides the JSON
representation of your models arguarbly being a presentation concern, trying
to cram all of this logic into an `#as_json` method quickly turns into pure chaos.

There are a few other json templating libraries available, but I wasn't satisfied with any
of the DSL's. So I created Bldr.

## Features

* Simple json templating DSL
* Uses Tilt's built-in rendering and template caching for better
  performance

## Installation

There are two ways to use Bldr in your Sinatra app, depending on whether
you are using Sinatra's classic or module application style:

```ruby

# Method 1: Classic style

require 'sinatra/bldr'

get '/hello' do
  bldr :hello
end


# Method 2: Modular style

require 'sinatra/bldr'

class MyApp < Sinatra::Base
  register Sinatra::Bldr
end
```

## Usage

See the [Documentation & Examples](https://github.com/ajsharp/bldr/wiki/Documentation-&-Examples) page on the wiki.

## Editor Syntax Support

To get proper syntax highlighting in vim, add this line to your .vimrc:

```
au BufRead,BufNewFile *.bldr set filetype=ruby
```

## TODO

* Rails 3 support
* Replace current_object with a block param for collection methods
* XML support

## Acknowledgements

* [RABL](http://github.com/nesquena/rabl) - Inspiration
* [Tilt](https://github.com/rtomayko/tilt) - Mega awesome templating goodness

## Contributors

* Ian Hunter (@ihunter)

## Copyright

Copyright (c) 2011 Alex Sharp. See the MIT-LICENSE file for full
copyright information.
