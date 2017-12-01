# hfagerlund.github.io

[![Build Status](https://travis-ci.org/hfagerlund/hfagerlund.github.io.svg?branch=master)](https://travis-ci.org/hfagerlund/hfagerlund.github.io)

My [GitHub Pages](https://pages.github.com/) site powered by [Jekyll](https://jekyllrb.com/) using [docSkimmer theme for Jekyll](https://github.com/hfagerlund/jekyll-docskimmer-theme).

Currently serves as a [table of contents](https://hfagerlund.github.io/) listing of [my open-source projects on GitHub](https://github.com/hfagerlund/).

[[Visit my Jekyll site](https://hfagerlund.github.io/)]

## Theme updates

Use the following steps to keep the [GitHub Pages project](https://github.com/hfagerlund/hfagerlund.github.io) in sync with updates to the [theme project](https://github.com/hfagerlund/jekyll-docskimmer-theme):

```bash
# using subtree merge strategy -
## clone the GitHub Pages project
git clone https://github.com/hfagerlund/hfagerlund.github.io.git
cd hfagerlund.github.io
## add the theme project as a git remote ('theme_remote')
git remote add theme_remote https://github.com/hfagerlund/jekyll-docskimmer-theme.git
git fetch theme_remote
## create branch **before** merging theme updates
git checkout -b theme-updates-branch theme_remote/master
git checkout master
## read content of the (latest) tree-object into 'jekyll-docskimmer-theme' (sub)directory
git read-tree --prefix=jekyll-docskimmer-theme/ -u theme-updates-branch
git merge --squash -s subtree --no-commit theme-updates-branch
git commit -m "subtree merged into master"
git checkout theme-updates-branch
git pull
git checkout master
git merge --squash -s subtree --no-commit theme-updates-branch
git add -A
git commit -m "adds latest theme updates"

```

## License

Copyright (c) 2017 Heini Fagerlund. Licensed under the [Simplified BSD License](https://opensource.org/licenses/BSD-2-Clause).
(See [LICENSE](https://github.com/hfagerlund/hfagerlund.github.io/blob/master/LICENSE).)
