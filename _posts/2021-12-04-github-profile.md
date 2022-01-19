---
layout: post
title: Custom Github Profile
description: A little over a year ago Github introduced profile customization through a custome README.
date: 2021-12-04
---

So, it seems I am a bit late to the party, but here nonetheless. A little over a year ago Github introduced profile customization through a custome README. To create your own, all you need to do is create a repo named after your username and then modify the `README.md`. Anything you place in this special repo will be displayed as your custom profile, you can see mine below.  Trust me, it isn't hard to cobble together a pretty slick profile. 

<figure>
  <img alt="Github Profile" src="/assets/images/github-profile.jpg" />
  <figcaption>Fig.1 - https://www.github.com/acavella/</figcaption>
</figure>

### The Header
I build my header image using [canva](https://www.canva.com). It is free to use and if you are like me and have no real skills when it comes to graphic design, it takes away the guess work. Choose one of the social media banner templates to get started, overlay your name or some catchy text and save it. Place the image in your repo in a folder named `assets` or similar.

### The Badges
My profile README has a number of badges; social, github stats, and technologies.  These are built from a number of sources and you can find plenty of help on how to implement them.  The Github stats are curtosy of [git-badges](https://pufler.dev/git-badges/). The social links and technology badges are a combination of [Simple Icons](https://simpleicons.org/) and [ShieldIO](https://shields.io/). 

### The Feed & Quotes
This part of my README is actually dynamically generated and is based off the tutorial provided by Brandon Coyer and his excellent tutorial [Creating a Killer GitHub Profile README](https://daily.dev/blog/creating-a-killer-github-profile-readme-part-1). An hourly Github Action runs and populates my README with links to my latest blog posts via RSS feed.  The quote pulls a random quote from The Office courtesy The Office API.  

### Conclusion
It's super easy to add a little bit of style and interest to your Github profile. If anything you see on my own inspires you, feel free to grab it. Good luck!
