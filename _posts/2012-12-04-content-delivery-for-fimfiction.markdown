---
layout: post
title: Content Delivery for Fimfiction
---

[This post](http://www.ponychan.net/chan/fic/res/121064.html#125218) on Ponychan got me thinking, how plausible would it actually be? You might see my initial reaction further down in the thread, but I thought on it a bit longer, and what kind of data does such a system actually need?

I'm thinking that I could develop a website that does the job. I know, I know. I'm crazy. Let's just put that aside for now. [The story API](http://www.fimfiction.net/api/story.php?story=6762) gives a lot of useful information, and the people who have favourited a story are publicly available on [the stats page](http://www.fimfiction.net/index.php?view=referrers&story=6762). If the gods be merciful, knighty might even put a bit more data in that API.

The public-facing side of the website would be very simple to use (and consequently, develop). It would have two main functions: "Recommend me something" and "Find me something like this". The recommendations would have stuff like the synopsis, cover pic, etc., followed by options like "Read this now", "Maybe later", and "Not interested". The first option would be a link to the story on Fimfiction and, when clicked, changes the options to things like "Recommend" and "Do not recommend". The second and third options will produce another recommendation, with the latter letting the system know to never recommend that story again to that person.

I'm still brainstorming all the different kinds of data that might be used, but I'm seeing a lot of options that certainly might work. The biggest hurdle to overcome is getting people to use the system. There isn't much of a solution to that other than to make it and wait for people to use it.

People could feed the system a bunch of stories they'd recommend as story URLs. (This is how I imagine stories would go into the system, rather than me hitting the site with thousands of requests one day followed by angry letters from knighty.)

To synchronise data as much as possible, I'd have it so that your username and Fimfiction username have to be the same. People could verify they own the account by putting something in their Fimfiction bio which the site could check against, most likely using that "Other accounts" field in "Edit account options". (This might come across as advertising, but people could edit it out after verification if they so desired.) I'd also have to very clear that they should use a different password from their actual Fimfiction account, because people are stupid about that kind of thing and I don't want to deal with the whole password-stealing accusation thing that's sure to come up.

The types of data available for the algorithm from Fimfiction are numerous: views (per chapter and total), favourites (who and how many), groups, word count (per chapter and total), tags (number and type), content rating. The site could have data from feedback on the system, e.g., "was this recommendation accurate?" and "would you recommend this story?"

The "Find me something like this" and "Recommend me something" algorithms would have to have different feedback mechanisms, since one is saying "This is like that" and the other is saying "You'll like this", and the user has to let the system know if it's right or wrong for those different reasons.

In short, it's a third party content delivery system for Fimfiction. It might crash and burn horribly, but my curiosity makes me want to try it. And by God, if it works, it'll be amazing.

I'll be doing a lot of research into things like Pandora and how they work. I'm still in the planning stage here, of course. Any thoughts or spitballing would be welcome and awesome.
