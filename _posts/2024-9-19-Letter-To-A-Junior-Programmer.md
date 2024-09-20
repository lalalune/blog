---
layout: post
title: Letter To A Junior Programmer
---

I've been doing this a long time, and I've learned some stuff. A lot of the reasoning for why is simply learned experience, and to give you that experience I'd have to tell you long boring stories. Here are some notes which have been bouncing around my head which may be useful to you and, should you heed them, may save you a great deal of pain and time.

The most common mistake that engineers make is optimizing the wrong things. You should always ask yourself questions like "what am I *really* doing? What are the hours I put in supposed to get out? Am I achieving that goal optimally?" If we don't ask ourself these questions every hour of every day, we might spend a lot of time going down the wrong rabbit holes.

Everything you think you know about programming languages is probably incorrect, but it's okay and you're not alone. Programming is the most complex puzzle ever created, and it's evolving every day. You can spend your life on reddit arguing about which language is best, or which framework is best, but people make millions of dollars coding PHP in their underwear. What matters is "what's going to help our business meet its goals with the resources we have?"

All the code you see is iterative. It's never finished, it was merely iterated to the point where it stopped producing bugs. Writing code is expensive, especially in the beginning phase when you have no users or revenue, so as a rule, profitable code tends to be sloppy. If you're coming into a successful project with awful code then you should assume that the team before you was optimizing for delivery speed, not code quality.

Startups are inherently very, very chaotic. Unless you've been the CEO, it is hard to imagine just how many things a CEO actually has to do to keep a company running and compliant. If you are at a company that has raised enough or is making enough to hire you, then you are working for people who have gotten further than most, and they definitely have a lot of fish to fry. Your job is to be a good soldier and not waste their time. They are giving you the opportunity to get paid to learn valuable life skills in exchange for your loyalty and dedication to the success of their dream. Don't take it lightly.

Complex software is not elegant. High performance code is almost always ugly. Many things that would make nice, readable code can also cause huge memory allocations, cache misses, and other performance issues. It is generally true that code gets uglier as it gets faster. If you see ugly code doing something fast, that's probably what is happening. A lot of code doesn't need to be performant, and it's better to just keep it elegant and simple. Only make things ugly if you have to, and only when performance becomes a bottleneck.

Complexity is your worst enemy. Simple code is easy to read, easy to share, easy to spot bugs in and fix. If you have an object that does something, all of the things it does and all of the data it contains should be in one place and easy to find in that place. The less someone else has to click through different files and functions to understand how something works, the more likely they are to understand it and be able to meaningfully improve it.

You can repeat yourself once. You can repeat yourself twice if it would require more code to abstract something than to just have it twice. Once you start copying and pasting a bunch of fragile code into every file then you should probably put the code in a shared library or module, but if it can be ctrl+f and replaced then leave it and focus on shipping. Don't waste time refactoring or adding abstraction and complexity just so you don't have to repeat something.

When more experienced engineers give you feedback, it's probably from pained experience at the cost of many wasted hours. When people explain things to you, it's not because they think you're dumb but because there is a technical need to be clear and thorough. The less you say "I know" to people who are trying to teach you something, the more you'll end up learning.

You need to be using what you're building constantly. You need to really understand and empathize with the user experience and see your hours invested from their perspective. *"Wait, the engineer spent all day making the variables conform to the style guide? But the search bar isn't working!"* It is very easy and often addictive to work on shiny things or completely ignore actually testing the product you're building, and this is one of the biggest pitfalls that engineers fall into. I would argue it's the number two reason I've seen startups fail, after cofounder drama. Every single person on a small team who has any connection to the product should use the product every day, and if they don't then they should not be there.

If I could boil it all down, it's just about seeing the big picture. You're just one person in this whole project, and the work you're doing is a means to an end. Focus on the end, and the shortest path there. You'll be able to give a lot more value to people with a lot less effort if you listen to their actual needs and meet those and ignore everything else. All the startup books and management guides you could read essentially boil down to: build things people will buy, then optimize that process as much as possible. It's the same thing. Big picture.

Feel free to reach out to me any time for anything. I'm always happy to help.

But if you figure it out on your own, that's even better.