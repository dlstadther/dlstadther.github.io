---
layout: post
title: "From Gitbook to Mkdocs"
date: 2022-01-17
categories: ['code', 'deployment', 'devops', 'git']
---

This post will serve as a reminder for motivation and example for moving from Gitbook to Mkdocs for [Github Pages-hosted](https://dlstadther.github.io/cheatsheets) and Github Actions-built cheatsheet document publication.


## Motivation

As of early 2020, I had converted a `git` blog post from a post to a "cheatsheet" website using Gitbook. That blog post can be found [here](https://dlstadther.github.io/blog/2020/04/25/gitbook-gh-pages).

However, when I went to add to a new "cheatsheet" in late 2021 I found that the CI/CD for Gitbook was failing.

Given that I'm writing this retrospective many months after-the-fact, I cannot recall the exact errors I was encountering. The long-and-the-short of it was that Gitbook was not supported in the opensource capacity that it once was and I needed to replace my usage of it within something else.

## Alternatives

When moving away from Gitbook, my requirements were:
1. input multiple files
1. input files in markdown
1. generate static web content (and serve with Github Pages)
1. easy to build artifacts via Github Actions

I entertained a few options:
* Pandoc
* LaTeX
* Sphinx
* Mkdocs

## Mkdocs

Ultimately, I went with Mkdocs. Mostly because their documentation was very straight forward to get started. In a matter of 15 minutes, I had a basic replacement of my "cheatsheet" website running locally. An hour later, my entire project and CI/CD had been replaced and I washed my hands of the aforementioned Gitbook errors.

I won't go into details _how_ I implemented Mkdocs here, or how exactly I migrated from Gitbook to Mkdocs. However, I will link to the Pull Request I submitted (to myself) to show the file changeset.

[Pull Request, replacing Gitbook with Mkdocs](https://github.com/dlstadther/cheatsheets/pull/1/files)
