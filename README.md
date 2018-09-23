# hfagerlund.github.io

[![Build Status](https://travis-ci.org/hfagerlund/hfagerlund.github.io.svg?branch=master)](https://travis-ci.org/hfagerlund/hfagerlund.github.io)

My [GitHub Pages](https://pages.github.com/) site powered by [Jekyll](https://jekyllrb.com/) using [docSkimmer theme for Jekyll](https://github.com/hfagerlund/jekyll-docskimmer-theme).

Currently serves as a [table of contents](https://hfagerlund.github.io/) listing of [my open-source projects on GitHub](https://github.com/hfagerlund/).

[[Visit my Jekyll-powered GitHub Pages site](https://hfagerlund.github.io/) > ]

---
## Important - Re: GitHub Pages compatibility

This branch of the project (ie. `master`) is [published on GitHub Pages](https://hfagerlund.github.io/). Modifications have been made to the directory structure of the **gem-based theme** [jekyll-docskimmer-theme](https://github.com/hfagerlund/jekyll-docskimmer-theme), as well as (minimal) [configuration file modifications](https://github.com/hfagerlund/hfagerlund.github.io#theme-updates) for compatibility with GitHub Pages.

For a directory structure that is compatible with gem-based themes without any modification, refer to the branch `use-with-jekyll-v3.2-and-above`:

```
$ git clone https://github.com/hfagerlund/hfagerlund.github.io.git
$ cd hfagerlund.github.io
$ git checkout -b use-with-jekyll-v3.2-and-above origin/use-with-jekyll-v3.2-and-above
```

---

## Theme updates

### After [Nov. 29, 2017](https://blog.github.com/2017-11-29-use-any-theme-with-github-pages/):
(As of March 25, 2018) The site is now configured to [**automatically** receive theme (style) updates](https://blog.github.com/2017-11-29-use-any-theme-with-github-pages/) from the [jekyll-docskimmer-theme](https://github.com/hfagerlund/jekyll-docskimmer-theme) project.

### Before Nov. 29, 2017:
Use the following steps to keep the [GitHub Pages project](https://github.com/hfagerlund/hfagerlund.github.io) `master` branch in sync with updates to the [theme project](https://github.com/hfagerlund/jekyll-docskimmer-theme):

```bash
$ git clone https://github.com/hfagerlund/hfagerlund.github.io.git
$ cd hfagerlund.github.io
$ git clone https://github.com/hfagerlund/jekyll-docskimmer-theme.git
## move directories out of theme dir into root
$ mv jekyll-docskimmer-theme/{_includes,_layouts,_sass} .
$ mv jekyll-docskimmer-theme/assets/* ./assets
$ rm -r jekyll-docskimmer-theme
## modify files
$ sed -i 's/theme: jekyll-docskimmer-theme//g' ./_config.yml
$ sed -i 's/{{ site.theme }}/jekyll-docskimmer-theme/g' ./assets/css/style.scss
$ sed -i '/jekyll-docskimmer-theme/d' ./Gemfile
## generate new Gemfile.lock
$ bundle install

```

## License

Copyright (c) 2017 Heini Fagerlund. Licensed under the [Simplified BSD License](https://opensource.org/licenses/BSD-2-Clause).
(See [LICENSE](https://github.com/hfagerlund/hfagerlund.github.io/blob/master/LICENSE).)
