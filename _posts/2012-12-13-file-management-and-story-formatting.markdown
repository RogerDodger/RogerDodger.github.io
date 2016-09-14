---
layout: post
title: File Management and Story Formatting
---

To no one's surprise, two of the more basic things to do with regards to story writing are the ones most often ignored. It always comes back to bite them one day, of course, when they submit their story to one of my contests littered with `[center]` tags, or when their publisher wonders what all these ugly BBCodes are littering their story, or when they open their `Stories` folder to 100 different items---half of which are entirely inappropriately named. (Let's not even go into people who don't make backups. It's said there are two kinds of people: those who make backups, and those who soon will.)

I don't think Google Docs (or Drive) is a good idea for storing your documents. It's a lot of unnecessary complexity when all it really needs to do is cloud storage. There are plenty of better-suited programs for writing documents (which we'll get to in a moment).

More to the point, I don't like having to be online to do my work. If you're anything like me, the computer is somewhat of a panacea. It does everything for you---social, playful, educational. It's fantastic. But when you need to focus, all of these features become inherent distractions. Sometimes, pulling the plug is the only way to lull your mind out of this constantly connected state.

I use [Dropbox](http://dropbox.com). It does one thing and it does it right: syncs a folder with the cloud. That's it. If you're not connected, it doesn't matter, because everything you're working with are plain files that your computer can recognise. This covers the problem of backups and of using multiple machines.

Anyway, moving on.

File management. If you have at least some semblance of organisation, you have a `Stories` folder or some such located somewhere on your hard drive. (I do pray that no one litters their root `Documents` folder with stray stories.) But what does this folder look like? Here's mine:

{% highlight bash %}
~/Dropbox/fic/Stories$ ls
A Deck with No Hearts  Inconsequential            The Assassin
Black and White        Lasting Impression         The Typographer
Business As Usual      My First New Years Alone   Wings of Icarus
Equine Descent         One Last Try
Fred                   Piercing Octaves
{% endhighlight %}

Yes, those are all folders. You should have a folder for each and every one of your stories. A story's folder is an ecosystem in which resides every resource that might come in handy for that story. If it's a complete shot-off-the-brain story that you did in an hour, then it might be true that one file is good enough. But for any story worth its salt, you're going to have a file for notes, a file for your plan, a file for the synopsis, a (possible) file for the cover art, and a file for the actual story itself. What if the story is multi-chapter? Would you name your files "Piercing Octaves - Chapter 1.docx", "Piercing Octaves - Chapter 2.docx", etc? Of course not. Look how much neater this is:

{% highlight bash %}
~/Dropbox/fic/Stories$ ls Piercing\ Octaves/
Ch1.lyx  Ch2.lyx  Index.lyx  Notes.md  Synopsis.md
{% endhighlight %}

Convinced? All right, moving on.

### Software ###

It's easy to get caught up in this, but the trick is to sit down and count your criteria. What do you need in a word processor, really? A spellchecker, and... yeah, that's about it. (A find and replace tool is a given – even Notepad has one of those.) You're probably going to submit your stuff to Fimfiction, which only takes plain text input, so you may as well write your story in plain text.

Considering this, I suggest a program that Ezn recommended called [FocusWriter](http://gottcode.org/focuswriter/). It's got a great interface (i.e., almost no interface), and boots up in full screen. All you get is a blank page. There are no buttons or widgets or gadgets to doodle around with – only a blank page. By default it saves your work in Rich Text Format, but I'd disable that and go with plain text.

If you want a full office suite for whatever reason, [LibreOffice](http://www.libreoffice.org/download/) is amazing. It opens in like half a second, and it does everything the less-hip corporate monolith Microsoft Word can. (Full disclosure: it can't, but none of the crap MSWord can do exclusively you'll actually need for writing fanfiction.) Don't use OpenOffice; it's abandoned and has an interface stuck in 1995.

Aside from those, you'll probably want a dictionary/thesaurus. People on \*nix systems can install the `dict` utility and get the definition and synonyms of a word by calling `dict <word>` in a terminal. For the rest of you Windows folks, there's [WordWeb](http://wordweb.info/free/) and [GoldenDict](http://goldendict.org/) for client-side resources, and [merriam-webster](http://merriam-webster.com) as an online resource.

### Formatting ###

This is the real hard one, because there's more than one way to skin a cat. Depending on your criteria, you'll probably end up with a different solution.

First up, the easy stuff: smart quotes and dashes. If you don't already know what the deal with dashes are, check [this article](http://eznguide.neocities.org/#Dashes-hyphens-and-ellipses-a-technical-note).

Most word processors will do the smart quotes for you, so no problems there. (If you don't trust word processors, check out [SmartyPants](http://daringfireball.net/projects/smartypants/).) Just be careful about leading apostrophes: *’tis*, *’taint*, *’ello*, etc – those should all look like little 9's, *not* 6's. An apostrophe does not turn heel merely because it's placed at the start of a word.

What about the dashes? Well, some word processors can do an auto-complete for you if you're using spaced en dashes, but I think some of them have a bit of trouble with em dashes. Easy solution: use two hyphens for an en dash, or three for an em dash, then do a find and replace when you're done.

Now the real kicker: how do you mark up your **bold** and *italics*? Well, that's the one that really depends on what you wanna do. A lot of people could just mark it up with the BBCodes, and submit it right away to Fimfiction. For those of you who want to get reviews done through Google Docs, you can copy the HTML output from Fimfiction into Google Docs for the intended effect. For most people, that'd be just fine.

Well, that's not so hard, is it? Don't worry, I can still confuse you yet.

Personally, I'd rather use Markdown or LaTeX. (Don't worry about the latter one unless you're doing some kind of computer science, mathematics, or engineering work, though. It's more focused on fancy maths stuff than writing pure prose.) Markdown, on the other hand, is a great lightweight language that's readable even when not converted to anything. [Here's an online editor.](http://dillinger.io/) I've written a few of my works and a good number of miscellaneous documents with it, because all you need is a text editor, and there are an absurd number of output formats, including "HTML, PDF (by way of [LaTeX](http://en.wikipedia.org/wiki/LaTeX)), [OPML](http://en.wikipedia.org/wiki/OPML), or OpenDocument (specifically, Flat [OpenDocument](http://en.wikipedia.org/wiki/OpenDocument) or `.fodt`, which can in turn be converted into [RTF](http://en.wikipedia.org/wiki/Rich_Text_Format), Microsoft Word, or virtually any other word-processing format)". There is, of course, to make things interesting, no direct conversion from Markdown to BBCode (not in [MultiMarkdown](http://fletcherpenney.net/multimarkdown/), anyway). Never mind that, though, because HTML to BBCode conversions are easy as pie. [Here's an online one.](http://skeena.net/htmltobb/index.pl)

Alternatively, you could drop the HTML output into Google Docs, and then use Fimfiction's Google Docs importer (and we all know how accurate that is).

Albeit that learning a scripting language and basic regular expressions could probably go a long way as well.

At the end of the day, though, fancy formatting sort of gets away from the point of writing prose, dunnit? I don't even end up using any of this stuff much. I don't think there's much need for anything beyond italics, really.

### Closing ###

I fear I have not helped make this any clearer in any way. Ah well. If there's one bit of good advice in here, it's to make a new folder for each story. You sure as sugar don't want to stumble upon a `Notes.txt` that contains various bits and pieces from *different stories*, only to then realise what you were actually looking for is in `ShippingNotes.txt`.
