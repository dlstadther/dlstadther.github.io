---
layout: post
title: "Github Pages - Setup and Development"
date: 2018-07-20
categories: code deployment devops
---

The following will serve as a self-reminder for how this blog was setup on Github Pages.

# Setup Steps

1. Setup Local Development Environment
2. Initialize with sample jekyll blog structure
3. Created repo `<username>.github.io`
4. Push local repo to remote
5. Update repo settings to enable Github Pages


## Setup Local Development Evironment

We need a couple things for Macos development:
1. Homebrew
2. Ruby
3. xcode-select
4. Gems: Bundler and Jekyll

### [Homebrew](https://brew.sh/)

```shell
$ /usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```

### [Ruby](https://jekyllrb.com/docs/installation/#homebrew)

```shell
$ /usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
$ brew install ruby
$ ruby -v
```

### xcode-select

```shell
$ xcode-select --install
```

### Gems: Bundler and Jekyll

```shell
$ gem install bundler jekyll
```


## Initialize with sample jekyll blog structure

Installs default minimal theme, [minima](https://github.com/jekyll/minima).

```shell
$ jekyll new dlstadther.github.io
```


## Create repo `<username>.github.io`

1. `github.com`
2. New repository
3. Repo metadata
    * Repository name: `dlstadther.github.io`
    * Description: `Personal Webpage powered with Github Pages and Jekyll`
    * Public
    * No initialization contents


## Push local repo to remote

```shell
$ cd dlstadther.github.io/
$ git remote add origin git@github.com:dlstadther/dlstadther.github.io.git
$ git add .  # bad practice, but notes intention
$ git commit -m "Initialize repo"
$ git push origin master
```


## Update repo settings to enable Github Pages

1. `github.com/dlstadther/dlstadther.github.io/settings`
2. Enable Github Pages
3. Source branch: `master`
4. Enforce HTTPS


# Development Process

As blog posts take awhile for me to write, a post will need to sit somewhere under version control where it will not be compiled and displayed with completed articles.

For this reason, a `_draft/` exists.

I create a file with the following [Front Matter](https://jekyllrb.com/docs/frontmatter/) contents:

```markdown
---
layout: post
title: "Sample Draft Blog Post"
date: 2018-06-28
categories: setup guide notes
---

```

and save it with the title `_draft/sample-draft-blog-post.md`.

Throughout the writing process, I will desire to see the compiled version of my work-in-progress. I am able to do so by the following:

```shell
$ cd dlstadther.github.io/
$ jekyll serve --drafts
```

then navigate to `http://127.0.0.1:4000/`. When done in this "debugging" draft mode, just `ctrl-c` to stop the jekyll process.

Once I reach contentment with a post, I update the Front Matter date to the current date and move the draft to posts with a modified filename.

```shell
$ mv dlstadther.github.io/_drafts/sample-draft-blog-post.md dlstadther.github.io/_posts/2018-07-20-sample-draft-blog-post.md
```

And of course add, commit, and push with git.

Then voilà, a new blog post!
