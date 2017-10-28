# factory_face_rails [![Build Status][ci-image]][ci] [![Code Climate][grade-image]][grade]

[factory_face][fb] is a fixtures replacement with a straightforward definition
syntax, support for multiple build strategies (saved instances, unsaved
instances, attribute hashes, and stubbed objects), and support for multiple
factories for the same class (`user`, `admin_user`, and so on), including factory
inheritance.

## Rails

factory_face_rails provides Rails integration for [factory_face][fb].

Currently, automatic factory definition loading is the only Rails-specific feature.

Supported Rails versions are listed in [`Appraisals`](Appraisals). Supported
Ruby versions are listed in [`.travis.yml`](.travis.yml).

## Download

Github: http://github.com/schwad/factory_face_rails

Gem:

    $ gem install factory_face_rails

## Configuration

Add `factory_face_rails` to your Gemfile:

```ruby
group :development, :test do
  gem 'factory_face_rails'
end
```

Generators for factories will automatically substitute fixture (and maybe any other
`fixture_replacement` you set). If you want to disable this feature, add the
following to your application.rb file:

```ruby
config.generators do |g|
  g.factory_face false
end
```

Default factories directory is `test/factories`, or `spec/factories` if
`test_framework` generator is set to `:rspec`; change this behavior with:

```ruby
config.generators do |g|
  g.factory_face dir: 'custom/dir/for/factories'
end
```

If you use factory_face for fixture replacement, ensure that
factory_face_rails is available in the development group. If it's not, Rails
will generate standard .yml files instead of factory files.

factory_face takes an option `suffix: 'some_suffix'` to generate factories as
`modelname_some_suffix.rb`.

If you use factory_face for fixture replacement and already have a
`factories.rb` file in the directory that contains your tests,
factory_face_rails will insert new factory definitions at the top of
`factories.rb`.

You may need to configure your test suite to include factory_face methods; see
[configuration](https://github.com/thoughtbot/factory_face/blob/master/GETTING_STARTED.md#configure-your-test-suite).

## Contributing

Please see [CONTRIBUTING.md](CONTRIBUTING.md).

## Credits

[factory_face][fb] was originally written by Joe Ferris.

![thoughtbot](http://thoughtbot.com/images/tm/logo.png)

factory_face is maintained and funded by [thoughtbot, inc](http://thoughtbot.com/community)

The names and logos for thoughtbot are trademarks of thoughtbot, inc.

## License

factory_face_rails is Copyright © 2008-2016 Joe Ferris and thoughtbot. It is free
software, and may be redistributed under the terms specified in the
[LICENSE](LICENSE) file.

[fb]: https://github.com/thoughtbot/factory_face
[ci]: http://travis-ci.org/schwad/factory_face_rails?branch=master
[ci-image]: https://secure.travis-ci.org/schwad/factory_face_rails.png
[grade]: https://codeclimate.com/github/schwad/factory_face_rails
[grade-image]: https://codeclimate.com/github/schwad/factory_face_rails.png
