---
layout: post
title: "Adding Github's Contribution Graph to Jekyll Website - Part 1"
date: 2018-07-24
categories: ['code', 'jekyll', 'javascript', 'github']
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

I decided to combine both of the aforementioned features (plus css formatting and randomization of graph base color). The result turned out quite nice!

{% include gh_contributions.html %}

Up-to-date code for this can be found at [/\_includes/gh_contributions.html](https://github.com/dlstadther/dlstadther.github.io/blob/master/_includes/gh_contributions.html). But at the time of writing:

<script src="https://gist.github.com/dlstadther/cb34932211531a8d9543843ebb67c640.js"></script>

This satified my base desire - to have my Github Contribution Graph on a website other than Github. However, one keep component was missing - the commit count.


## Method 2: [Github Contributions Chart Generator](https://github.com/sallar/github-contributions-chart)

Method 1 had a few shortcomings of which I wasn't a huge fan.

1. Commit count is not included
2. Url response is slow
3. Only includes past year

In pursuit of the unicorn to satify my desires, I found a few projects by [@sallar](https://github.com/sallar) which appeared to be promising.

### Version 1 (static img)

I first came upon [@sallar](https://github.com/sallar)'s hosted contribution image generator, [github-contributions.now.sh](https://github-contributions.now.sh/).

For a static solution, this was exactly what I was looking for!

![Yearly Github Contributions (static)]({{ "/assets/img/gh_contributions_yearly.png" }})

### Version 2 (dynamic img)

Ideally, I don't have to manually update and upload an updated image every so often.

Thankfully, [@sallar](https://github.com/sallar) also opensourced the backbones of his hosted contribution image generator:
* [Github Contributions API](https://github.com/sallar/github-contributions-api)
* [Github Contributions on Canvas](https://github.com/sallar/github-contributions-canvas)

I'm not yet sure if/how I can interact with these projects while continuing to utilize Jekyll and Github Pages. Nevertheless, efforts will be made.

To avoid this post sitting idle for too long, a future post will be made continuing on this topic...
