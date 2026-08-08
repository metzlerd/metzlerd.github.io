# don-metzler.net

Source for [www.don-metzler.net](https://www.don-metzler.net), a static Jekyll site
built and deployed automatically by GitHub Pages on every push to `master`.

## Editing content

The whole site is four pages, all in `_pages/`:

| File | URL | Notes |
| --- | --- | --- |
| `about.md` | `/` | Homepage |
| `bio.md` | `/bio/` | Third-person bio |
| `research.md` | `/research/` | Selected publications, articles, talks |
| `404.md` | `/404.html` | Not-found page |

Other things you may want to change:

- **Menu items** — `_data/navigation.yml`
- **Sidebar profile** (name, photo, links) — the `author:` block in `_config.yml`.
  Blank or omitted fields are simply not rendered; see `_includes/author-profile.html`
  for the full list of supported fields.
- **PDFs** (CV, resume) — `files/`, served at `/files/<name>.pdf`
- **Profile photo** — `images/profile.png`

## Running locally

Requires Ruby. On Windows, `winget install RubyInstallerTeam.RubyWithDevKit.3.3`.

```
gem install bundler
bundle install
bundle exec jekyll serve --config _config.yml,_config.dev.yml
```

The site is then at <http://localhost:4000>. Passing `_config.dev.yml` blanks the
Google Analytics tracking id, so local browsing is not recorded.

Note that `_config.yml` is *not* reloaded on change — restart the server after editing it.

## Rebuilding the JavaScript bundle

`assets/js/main.min.js` is a checked-in build of the files listed under `scripts.uglify`
in `package.json`. It only needs regenerating if you edit something in `assets/js/`:

```
npm install
npm run build:js
```

## Credits

Built on the [Academic Pages](https://github.com/academicpages/academicpages.github.io)
template, a fork of [Minimal Mistakes](https://mmistakes.github.io/minimal-mistakes/)
by Michael Rose, © 2016 and released under the MIT License (see `LICENSE`).
Unused template features (blog posts, collections, comments, talk map, archives)
have been stripped from this copy.
