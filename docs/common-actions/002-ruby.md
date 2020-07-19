# ruby

```yaml
- uses: actions/setup-ruby@v1
  with:
    ruby-version: 2.6.5
- run: |
    sudo apt-get -yqq install libpq-dev
    gem install bundler
    bundle install --jobs 4 --retry 3
    ruby src/url.rb
```
