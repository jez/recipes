# recipes

- Blog source is here on `master`.
- Blog compiled is via GitHub Actions (into `_site`, but not in `git`)
- Blog rendered is at <https://jez.io/recipes/>.

## Setup

```
rbenv install
bundle install
brew install pandoc
```

## Using

You might have to `dropbox stop` on Linux for inotify problems.

```
_bin/serve

bundle exec octopress new draft my-slug

bundle exec jekyll build
bundle exec octopress publish my-slug

bundle exec octopress new page

_bin/publish
_bin/build
```
