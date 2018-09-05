---
layout: post
title: "Zero to Maintainer in T-minus 270 days"
date: 2018-09-03
---

Over the course of 9 months, I grew from a community user to a maintainer of Spotify's Luigi - a Python pipeline framework. The journey from zero to maintainer was not an overnight event. What began as a work necessity turned into a personal time passion.

I began my investigation of Luigi due to a need to improve existing data warehouse batch ETL processes to a more flexible pipeline framework. However, through this migration process I found aspects of Luigi which didn't exist or didn't fully fit our needs. With it being an opensource project, I was able to investigate and submit pull requests to complete the functionality required to utilize Luigi in our use cases.

From initial product research to a fully migrated set of ETL processes, I worked with Luigi on a daily basis for 5 months. While my code no longer requires frequent update such that I'm still expanding on Luigi feature development, my interaction with Luigi has actually increased in frequency. But not in the role of a contributor.

Now-a-days, I spend time [nearly] everyday reviewing PRs, responding to design decisions, coordinating secondary reviews, and providing feedback to Issues. If anything, I spend more time on Luigi as an administrative maintainer than I ever did as an individual project contributor.

Of course, my maintainer role took quite some time to ramp up.

I wasn't very far into my career when I embarked upon my journey with Luigi. I hadn't even interacted with any other opensource project previously. When I began my utilization of Luigi, I didn't have intentions of growing into a leadership role with the project. However, I find that I am someone who desires to be use the best and be proud of that which I can (at least) [partially] call my own. If I was going to be represent Luigi as a contributor, I wanted the project to have a sterling appearance and reputation.

As time went by, I began seeing a dramatic slow down in Luigi contribution and activity (even from myself). Why was this happening? Was Luigi being beat by Airflow and other tools? Or were we developing an appearance of apathy and neglect?

I believe both are true. Airflow is the new, hot thing for Python workflow DAGs. But also, Luigi's repository was becoming muddy with stale PRs and Issues which were getting no attention. Don't get me wrong, I believe strongly in the Luigi community. However, we're all technical people with full-time jobs. Not all contributors and maintainers have the time to consistently respond to and review every submission. Some of us may not even still work with Luigi like we used to.

Still early in my career with moderate scheduling flexibility, I found myself in a position where I could make an impact. I'm no expert in all things Luigi, but I have developed a comfort in code review such that I foster contributor development while minimizing my hand-holding and overly in-depth grading. The most important part of code reviews is not an over encompassing review, but rather a series of quick back-and-forth questions, directions, and suggestions. Clear communication and speed help to move PRs along quickly.

However, not all PRs are good PRs. An unfortunate aspect of maintaining an opensource project is that sometimes you have to stand your ground that a feature addition or methodology doesn't belong. Technical debt is a serious project killer.

By no means am I a great maintainer. I like to think I do well. I don't do it to gain recognition or prestige. I do it because I enjoy mentoring and seeing groups of people come together to make an impact as one. In the case of Luigi, it is seeing the continued improvement of a Python package that many will come to use to fill a gap in which they have.

Two years have passed since I was entrusted with the joint role of a project maintainer and now I am generally the most active maintainer of Luigi. I've experienced the impact this role has had on my technical and non-technical growth and I look foward to the future of my continued responsibility.


Timeline:
* September 2015 - Introduced to Luigi
* October 21, 2015 - First [Contribution](https://github.com/spotify/luigi/pull/1331)
* June 5, 2016 - First [Merge](https://github.com/spotify/luigi/pull/1702) as Maintainer
* October 5, 2017 - First Luigi Release ([2.7.1](https://github.com/spotify/luigi/releases/tag/2.7.1))
* September 3, 2018 - "Zero to Maintainer" blog post


Maintainer Tips:
* Enable repo-wide notifications for PR and Issue engagement
* Automate where you can
    * Github's [CODEOWNERs](https://help.github.com/articles/about-codeowners/) is a good place to start for code reviews
    * [Probot's stale](https://github.com/probot/stale) is immensely helpful for cleaning a repo for orphaned submissions
* Respond to PRs and Issues quickly, even if just to say "Thanks for submitting, I'll take a look soon!" or "I'm not an expert on this area, but maybe @user might be able to provide additional guidance."
* Spend the extra few minutes crafting responses such that they're clear in content and intention
    * We don't all share the same primary language, so do what you can to reduce the need to excessive back and forth conversations to clarify each other's intentions
* Be patient
