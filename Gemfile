source "https://rubygems.org"

# The github-pages gem pins Jekyll and the plugins to exactly the versions
# GitHub Pages runs, so a local build matches what gets published.
#
#   bundle exec jekyll serve --config _config.yml,_config.dev.yml
#
gem "github-pages", group: :jekyll_plugins

group :jekyll_plugins do
  gem "jekyll-feed"
  gem "jekyll-sitemap"
  gem "jekyll-redirect-from"
  gem "webrick", "~> 1.8"   # no longer bundled with Ruby 3+
end

# Windows has no system zoneinfo database, so the `timezone:` setting in
# _config.yml makes tzinfo fail with DataSourceNotFound. This gem ships the
# database as pure Ruby. GitHub Pages builds on Linux and doesn't need it.
gem "tzinfo-data", install_if: -> { Gem.win_platform? }

# Note: the "wdm" gem used to be listed here for faster file-watching on
# Windows. It does not build against Ruby 3.3+ (it calls the since-removed
# rb_thread_call_without_gvl) and is unmaintained. Jekyll falls back to
# polling without it, so it has simply been dropped.
