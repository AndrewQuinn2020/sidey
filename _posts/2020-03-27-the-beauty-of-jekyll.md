---
layout: post
title: "The Beauty of Jekyll"
date: 2020-03-27
categories: computing
tags: happy precious-plaintext-vibes
---


Picture the following.

I boot up [Atom](https://atom.io/) to begin writing a blog post. I make a new Markdown file, hammer out a couple of paragraphs. My writing concluded, hit `Ctrl+S` on that bad boy.

Do I leave the fiddling and futzing to take my slightly nerdy `.md` file and convert it into Wordpress or whatever for another day, and just head to sleep? If I were working with that kind of process, probably; I'm a bit of a lazybones.

But I'm not working with that process. In fact, I do something very different -- something beautifully simple, ingrained into me from years and years of good programmer practices.

You see, first off, this `.md` file is actually saved inside of a git repo -- but, okay, that's not *that* unusual. Plenty of written materials exist on GitHub, even if we almost never actually have to bust out its more [DerAnG](https://atom.io/)ed history-bending features on them.

Atom happens to be built *by* GitHub, so I hit `Ctrl+Shift+9` to bring up the tiny little panel where I can `Stage All Changes`, then hit `Ctrl+Enter` to `Commit Staged Changes` (with a cheeky `commit` comment), and finally hit `Ctrl+Enter`,`Alt+G P` to commit and push changes to the repo. Up the pipeline it goes, to GitHub.

But there's something... *Odd* about this GitHub repo.

![Why are there so many other files in here besides the `.md` one we were just editing?](/images/3-27-2020-odd-repo.jpg)

Why are there so many other files in here besides the `.md` one we were just editing?

It turns out that all of those `.html` files and their ilk are what the static site generator [**Jekyll**](https://jekyllrb.com/) uses to work its magic.

## Jekyll: A dream come true

Jekyll is the kind of software I *dreamed* about when I was just starting out in my coding journey, over a decade ago.

Everyone who wants to put stuff on the web starts out by learning a bit of HTML and CSS. Maybe JS if they're hardcore. Most people very, very quickly realize there is *far* too much HTML, CSS, and JS in any webpage of real complexity to actually dig in and understand most of it. At best our hand-authoring is used for the occasional, manual, spot check; we leave actually generating the stuff to behemoths like Wordpress and other content management systems.

This always bugged me growing up. I correctly felt like this was *too much power being taken away* from me. Having grown up [reading my history](http://catb.org/~esr/writings/taoup/) I knew that this wasn't the way the old hackers would have wanted things to be either.

Besides, most of my favorite websites were (are) blogs. I don't really need, or even want, all that complicated analytics and stuff going on behind my back most of the time.

Why couldn't there just be a computer program where I could feed it in some plain text files, maybe lightly marked up, and have it spit out a decently functional -- but simple! -- website? Where I wouldn't be constrained to tossing my writing into some obscure CMS binary blog?

That's exactly what Jekyll is.

Jekyll, at its core, gives you a simple promise, after you get it set up (which my experience suggests takes about an afternoon, unless you really want to dive in deep and make something unique -- which you can!). You focus on writing the `.md` files. Let *me* handle actually generating a site for you.

And once I'm done, there'll be a nice little `_site` folder sitting right there, filled with `.html` files that you can open up and peruse in the leisure of your own web browser, locally, just like that first time you authored a webpage by hand. (Except they'll probably look much, much nicer. 😉)

A match made in heaven, right?

Almost.

# Netlify: Continuous integration for blogs

"Continuous integration" and "continuous deployment" are basically fancy programmer speak for, "I want you to do certain things *every* time I push a new commit to our GitHub branch".

Although I'm no pro, usually, I think of the excellent [Travis CI](https://travis-ci.org/) service when it comes to that stuff, which basically runs suites upon suites upon suites of software tests on your code-base every time you push up to the 'hub. Naturally this requires automatically running the code you want tested in some regard, right? So it's almost like an IFTTT trigger -- "New code? Okay, recompile and run all the tests again". Fantastic stuff.

But wait a minute. Blogs don't *have* tests they need to pass. They're literally just words. Why might this be useful? Well, suppose you have a bunch of `.md` files, and you can generate a really spiffy site with them just by running `jekyll build` in their parent directory...

And that's exactly what [Netlify](http://netlify.com/) does. **For free.**

If you set it up correctly (and this is considerably easy, much easier than Jekyll's setup in fact), then *every* time you push up new content to the GitHub repo where you're storing your `.md` blog posts, and maybe some images and stuff too, Netlify will kick into gear, generate a brand new `_site` on their end, and then **host it for you**.

This is *genius*, because those `_site`s are, well, static! There's very little overhead to just hosting a bunch of `.html`, `.css` and `.js` files. Static sites by definition don't do anything crazy server-side; any nice little effects are going to happen client-side, and that's that.

Oh, and if you happen to have a domain lying around on a place like [Hover](hover.com/), all it takes to link that domain to the new static site is changing the nameservers.

# Conclusion

I have a blogging workflow now that brings so much *joy* to my heart.

All of my posts are stored and written in plain text, just like back in the days of yore where I used to use `org-mode` to generate these kinds of things.

Yet when I push up to the 'hub, *wizards halfway across the globe* use Jekyll to render my little stack of plain text doohickeys into something... just... gorgeous. Absolutely stunning.

I won't say it's *all* good yet; I still need to figure out how to get MathJax working. But the combination of Jekyll + GitHub + Netlify + Hover for Nonstandard Deviations mgiht be my favorite Internet thing of the entire year.
