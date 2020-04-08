---
layout: post
title:  "Elm Bricks, Javascript Sand"
date: 2020-04-08
snippet: "Getting a feel for Javascript."
categories: posts
---

I’ve been working as a Javascript developer for about 6 months now. When I
first started it was hard. Coming from Elm, things just felt so different.
Stepping back a bit, one way to put it is:

> Elm feels more like Legos or bricks, while Javascript feels more like putty or
sand.

For example, in Javascript, if you want to add a bit of functionality you
usually just patch it right in. Maybe through another if statement, another
function call, another value in an object, maybe even an asynchronous operation
that you can just put anywhere and wait for. As you keep patching in these
small changes, a piece of your codebase that once felt like a little black box
now feels like a big amorphous ball that has gradually fused with a bunch of
other things.

In Elm, every piece of your codebase feels very walled off. You have the strict
type checking, you’re not allowed to have circular dependencies, and your
functions can’t have any side effects. So it’s like you’re putting together all
these little lego pieces and most of them won’t even fit together. On top of
that, the ecosystem is a lot smaller so you can’t just throw in some big piece
of complex functionality that you pulled off NPM or Stack Overflow.

I don’t think either approach is inherently better. Elm probably has a more
cohesive and theoretically sound design, but often what makes sense in theory
fails in practice. It’s like all the time spent thinking about the right way to
do things prevents people from actually doing things.

Elm is great, so is Javascript. Computers are great. People are great. Namaste
mother f***ers.
