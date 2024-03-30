---
title: "Simple analytics with CSS"
date: "2023-11-06"
categories: 
  - "code-experiments"
tags: 
  - "analytics"
  - "css"
  - "javascript"
---

I’m always fascinated about what is achievable without Javascript. So when I was reading this article about [how Bear Blog does analytics with CSS](https://herman.bearblog.dev/how-bear-does-analytics-with-css/), I decided to do my own experimentation. The concept here is to use css to trigger certain endpoints by using properties that require loading an image (or something).

To do this, I spun up an ExpressJS app and created a simple endpoint that started out with just outputting certain params. I kept it simple in the beginning as I just needed a feedback mechanism for the requests my CSS was making. If I were to use this somewhere, I would need some sort of data store to persist data. But otherwise, it would be quite simple.

The next step was to make the request look legitimate. I made myself a 1 pixel transparent dot to send back so that whatever image property I chose, the browser got this pixel back. Yes, this felt a bit old school to me but I gave myself some grace knowing I wasn’t hiding an image tag to load this dot.

I first tested on my local dev environment and then I used my phone to see how it worked in a mobile environment.

**Here are some of my learnings:**

- It’s great if all you need is some simple page views tracking and you’re not doing a single page app (though if you’re trying to avoid javascript, that wouldn’t be the case anyways).
- It has limited ability to do click tracking by leveraging the `:active` on most elements. I didn’t want to go with :hover because I wanted the same behavior on mobile and desktop. While `:hover` works for mobile taps, I don’t want tracking for anytime a mouse hover occurs on desktop.
- There was one downside to this method of tracking which is it’ll track each click/interaction the first time but since the browser has it loaded and cached, it won’t do it the second time. I know you can hack this with some javascript but I wanted to stay on the pure CSS route.

The thing I enjoyed the most about this was that it was really going back to basics. In a world where rendering a whole page using Javascript is a common thing, it’s nice to be able to just do some basic simple things and achieve a lot more with greater simplicity. Will this solution work for everyone? Probably not. But will it work for a basic website that just needs to see basic trends? Likely.

You can play around with the code I hacked around with by [checking out this repo](https://github.com/stephanie-gredell/css-analytics). It went a bit further than what I described here but you can get the general idea if you wanted to build out your own analytics app in Node.
