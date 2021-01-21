## Hugo + GitHubPages

The static website is hosted at the GitHub Pages endpoint for this repo. I decided to explore using the [Hugo](https://gohugo.io) static site generator to set up the environment, using the [Quickstart](https://gohugo.io/getting-started/quick-start/) guide to get started.

---


`STEP 1`:  install hugo for development.

```
$ brew install hugo
$ $ hugo version
Hugo Static Site Generator v0.80.0/extended darwin/amd64 BuildDate: unknown
```
---

`STEP 2`: Create a new hugo project (source directory)

```
$ hugo new site www
```

---


`STEP 3`: Add A Theme

Follow [theme directions](https://themes.gohugo.io/hugo-frances-theme/) - you should be able to substitute a different theme and use the same process.

```
$ cd www
$ git submodule add https://github.com/budparr/gohugo-theme-ananke.git themes/ananke
```

Some themes I've looked at:
 * [Ananke](https://github.com/budparr/gohugo-theme-ananke.git)
 * [Stack](https://github.com/CaiJimmy/hugo-theme-stack)
 * [Tranquilpeak](https://github.com/kakawait/hugo-tranquilpeak-theme.git)
 * [Frances](https://github.com/mcrwfrd/hugo-frances-theme.git)
 * [Coder](https://github.com/luizdepra/hugo-coder.git)

---

`STEP 4`: Customize Theme

First, edit the `www/config.toml` to specify the theme used

```
baseURL = "https://sketchnotes.dev/visual-azure"
languageCode = "en-us"
title = "Visual Azure"
theme = "coder"
```

Then, look at that theme's download/homepage for information on customization options and update the `www/config.toml` accordingly. 

---

`STEP 5`: Test your website presentation locally

This supports hot reload so you can see the impact of configuration and content changes to your websitee as you make them.

```
$ cd www/
$ hugo server -D
..
..
Web Server is available at http://localhost:1313/visual-azure/ 
(bind address 127.0.0.1)
```

---
`STEP 6`: BUILD FOR DEPLOYMENT

The default build directory is local.
Followed this [guidance](https://gohugo.io/getting-started/quick-start/) I updated my `www/config.toml` to specify a custom _publishdir_ ("docs") as the target.

Now just build the static website from this source using this command:

```
$ cd www/
$ hugo -D
```
 
`Note`: Go into the GitHub Settings for gh-pages and point it to the "docs/" folder. You static website is now automatically hosted at the GitHub Pages endpoint for this repo.


