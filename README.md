# Code Reviews with PRs Guide

### TL;DR

This guide guide is for people who'd like to spread good code review practices in their teams.

It aims to be a reference to show to your people, along with some good examples.

It takes elements from both [this post on github blog](https://github.com/blog/1943-how-to-write-the-perfect-pull-request) and [the thoughtbot guide](https://github.com/thoughtbot/guides/tree/master/code-review).


## Table of contents

- [Intro](#intro)
- [Anatomy of a PR](#anatomy-of-a-pr)
- [How to review other people's code](#how-to-review-other-peoples-code)
- [How to receive criticism and be more awesome](#how-to-receive-criticism-and-be-more-awesome)
- [Tips and tricks](#tips-and-tricks)
- [Good examples](#good-examples)
- [Bad examples](#bad-examples)
- [Glossary](#glossary)
- [Good resources](#good-resources)


## Intro

This guide is best suited for companies/teams using `github` or `github entreprise` to manage their code and code reviews, but the same principles apply elsewhere. 

It will try to explain the best practices on creating PRs, reviewing them, common ways of doing things, the `do`s and `don't`s, and we will cover the :shipit: squirrel.

## Anatomy of a PR

### What's a PR again ?

__PR__ is a `github`-specific concept which means `pull request`. You can [read on the official docs with plenty of screenshots](https://help.github.com/articles/about-pull-requests/), but essentially, 

> __PR is an UI for merging changes from one branch to another__, that allows discussion, pasting silly gifs, commenting on particular lines, and by doing that, documenting the change and the thinking behind for later (think onboarding a new person, or just refreshing your own memory).

### What code should go into a PR ?

The scope of a __PR__ will depend vastly on the actual changes that you are implementing, the project etc, but here are some guidelines:

#### Good PR

- bundles together __changes which are truly connected__
- __says exactly what it does__ on the tin
- __contains enough info for someone new to pick it up later__ and understand what's going on
- contains a __healthy dose of self-distance__
- makes use of the all the goodies available (lists, screenshots, links, etc).

#### Bad PR

- has __no description and/or uninformative title__
- __does more or less than it says on the tin__
- handles __issues which are unrelated__

### Building blocks of a PR

#### A branch. A good one.

__PR__ s are made by taking a branch, that you want to merge into another one. So for a good __PR__, you need a good branch discipline.

This is going to depend on the dynamics between the team members, but again, here's some stuff that tends to work well:

- __give the branch a reasonable name.__ Some common practices include adding prefixes, for example:
 - `fix/stale-connections-to-db`
 - `feature/add-paging`
 - `experiment/reimplement-proxy-in-go`
- __remove the branch after the PR is merged in__ (click the button at the bottom of the __PR__)
- __commit the changes in small, easily reversible increments__
- __apply logic and behave your best__

#### Description

Descriptions are written in Markdown, so they support all the goodies, like lists, code blocks, quotes, links, inline images, emojis, headers, etc. __Use them__.

> A __good description__ is one that you can dig out 6 months later, read, and:
- understand __why the change was needed__, 
- see clearly __what were the difficulties__,
- understand __what decisions were made and why__,
- and know __how to verify that it works__.


#### Dialogue

Reviewing other people's code doesn't have to be boring, and __the review shouldn't take more than 30 minutes__ (including checking out the code, running the tests and playing around). If it does, your __PR__ is probably too big.

Don't think I'm a nerd, but with a good use of [gifs](http://giphy.com/) and the `![](https://i.giphy.com/kFgzrTt798d2w.gif)` inline image tag, they can be really fun.



## How to review other people's code

When reviewing someone else's code, you are in the position of power. They did their work, their code is now under a microscope, and all the weaknesses are now going under a hammer. __Be careful__ to not use that position to be overly negative. It will be your turn soon, so treat people the way you'd like to be treated. Don't make enemies.

### Battlefield-proven techniques

- __don't be a dick__. You're looking at someone's work, and you should assume they are capable and well-meaning. If they are a weaker developer than you are, wait until your code gets under a microscope of someone stronger than you.
- __be humble__ - see point 1. The more you know, the more humble you get. 
- __help people grow__. You are here to help them avoid mistakes in the future and improve the overall quality of the product. Don't prove you're smarter or know more. Lead by example.
- __realise that most things are up for discussion__ and few are absolute truths. So don't present opinions as facts `supertest is better`. Use `I like supertest more, because it gives us A, B and C essentially for free`.
- __suggest, don't demand__. `What do you think of using Mock class here ?` always beats `use Mock class`. `I'm wondering`, `I think`, `Wouldn't it be` are your best allies.
- __use gifs and memes__ as long as that's your thing. They really have the potential to make everybody chill.
- __remember that things get often personal__, because the work produces is seen as a direct product of a person's capabilities. So, again, suggest, don't criticise.
- __when clarifying, use links__ to other repos, to a specific line. Cuts the communication required down very nicely.
- __talk in real life__. But after you do, put a comment with a summary of what you decided on.
- __be careful with sarcasm__. It goes well with some people, but often sounds much more harsh than intended, when read in isolation.
- __use code snippets to be explicit, but not show off__, when applicable.

You might have noticed, that the first three points are very similar. I wonder what that might mean ?

## How to receive criticism and be more awesome

In this situation, all of the little blibs and non-optimal solutions will be resurfacing, with your name attached to it. At the beginning it sounds little bit stressful, but here's a couple of guidelines to make it more manageable and fun:

### Guidelines

- __do your homework__ by prepping the PR properly (description, how to test, what's important to look at). Imagine a Michelin star restaurant meal vs a stale hamburger. No one flocks to dealing with your stale hamburger.
- __don't hide in the corner__. Hiding dodgy bits in a big __PR__ is not a working technique. Unless your goal is to enrage your colleagues.
- __don't take things too personally__. The code review process is there to catch all the mistakes and shady shortcuts, so dont' be surprised/embarassed/upset, when it does its job. The review is of a piece of code, and that piece only, not your capacities as a person. 
- __learn from each review__. Many people fall into a trap of thinking that they can't learn from a person below them on the paygrade. I personally think that everybody can teach me something, and it has always been true for me.
- __be grateful for the review__. Someone's essentially giving out the info that makes them a stronger dev than you are, and you are free to take it and we as awesome the next time. How cool is that ?
- __be responsive__. A stale __PR__ is like an old piece of pizza - still better than nothing, probably edible, but would have been much better two days ago.
- __invite people to review your PR__. It takes time to do it, so encourage them to do it for you. Don't dread being wrong - that's the best way to be right the next time.

## Tips and tricks

#### Close issues automatically, when merging a PR

You can specify which issues should be closes when merging. To do that, just say in the description `Closes #12` or `Closes http://github.com/seeker89/code-review-PR-quide/issues/1`.

#### Use inline gifs for fun and profit

The syntax is the following: `![](https://i.giphy.com/kFgzrTt798d2w.gif)`

#### Use multiline code snippets with proper color syntax

This is how you do that (specify the syntax after the triple "\`" sign):

```python
def time_to_roll():
    """Prints the essence of life""
    print("https://i.giphy.com/kFgzrTt798d2w.gif")
```

## Good examples


## Bad examples

Just kidding :smiley:. We won't be digging them out from the lurky search engine results... Or will we ?


## Glossary

- __[WIP]__ (also WIP, WiP) - _Work in Progress_. Means, that the __PR__ is not yet in its final form, but it's already been created to track comments, links, and get opinions. Often a better alternative to trying to keep a branch private, until you consider it ready to ship, because early suggestions might prevent mistakes.
- :shipit:, `:shipit:`, __squirrel__ - a sign, that one person sees the __PR__ fit of merging in. [The story about why that's a squirrel is long](https://www.quora.com/GitHub-What-is-the-significance-of-the-Ship-It-squirrel). Alternatives include :ship::it: and :sheep::it:.
- __LGTM__ - _Let's Get That Money_ - OK, let's ship it. Usually used, when no real review is required, because the change is small and obvious.
- __RFC__ - _Request For Comments_ (not github specific, but useful). Used when a draft of a design document is ready, and we talk on a much higher, abstract level of the idea described, more than the contents of the __PR__.
- __TL;DR__ - _Too Long; Didn't Read_ - most often used to introduce a very short description of the essence of the text that follows.

## Good resources

- [https://github.com/thoughtbot/guides/tree/master/code-review](https://github.com/thoughtbot/guides/tree/master/code-review)
- [https://github.com/blog/1943-how-to-write-the-perfect-pull-request](https://github.com/blog/1943-how-to-write-the-perfect-pull-request)
