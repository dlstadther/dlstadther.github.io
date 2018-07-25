---
layout: post
title: "[Re]learning Javascript with Github's Contribution Graph"
date: 2018-07-24
categories: ['code', 'javascript', 'github']
---

While relatively meaningless, I very much enjoy the comfort which my Github Contribution Graph brings me when I reflect on my growth as a professional developer.

I say the graph is meaningless for two reasons:
1. quantity > quality
2. easily abused
    * this can be accomplished through fake repos and back-dated commits

However, these graphs provide an easily digestable view into one's commit frequency.

Given my enjoyment of this graph, I decided to try to insert it here (on this site).

Note that Github does not (currently) provide an easy mechanism to extract this graph from one's Github Profile.

## Method 1: [Github Chart API](https://github.com/2016rshah/githubchart-api)

### Version 1 (inline)

My first method was to utilize [@2016rshah]()'s Github Chart API through a HTML `img` element right inside of Jekyll's markdown:

`<img src="https://ghchart.rshah.org/dlstadther"/>`

<img src="https://ghchart.rshah.org/dlstadther"/>

Cool, right?

Wait a second, isn't this post supposed to be about relearning Javascript?

While still on this method, I wanted to try out some other features using Javascript:
* custom graph colors
* Jekyll `includes`

### Version 2 (includes + color randomization)

I decided to combine both of these features (plus css formatting and randomization of graph color) and ended up with the following:

{% include gh_contributions.html %}

The code for this can be found at [/\_includes/gh_contributions.html](https://github.com/dlstadther/dlstadther.github.io/blob/master/_includes/gh_contributions.html).

This satified my base desire - to have my Github Contribution Graph on a website other than Github. However, one keep component was missing - the commit count.
