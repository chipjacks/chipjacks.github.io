---
layout: post
title:  "Four Line Layout"
date:   2020-12-29
snippet: "Define any layout with just four simple CSS classes."
categories: posts
---

One place I often get hung up starting a new project is on how to build the
layout. I can spend hours aimlessly browsing through all the latest CSS
frameworks, trying to make sense of the varying systems they use.  Or I'll
spend a bunch of time trying to decide whether to use `flexbox` or `grid`
for a particular `div`. Before I know it my morning is gone, and all I
have is an empty HTML page.

All I’m trying to do is arrange some rectangles! Why is
it so complicated? I noticed many layout systems were getting rid of fancy
terminology completely, instead opting for just rows and columns like
[elm-ui](https://package.elm-lang.org/packages/mdgriffith/elm-ui/1.1.8/Element#row),
or simply stacks like [Apple
UIKit](https://developer.apple.com/documentation/uikit/view_layout). I liked
this approach, but still didn’t want to commit to a new framework just so I
could arrange rectangles a bit easier.

Boiling it all down, I created four CSS classes that provide a small
abstraction over [`flexbox`](https://css-tricks.com/snippets/css/a-guide-to-flexbox/):

```css
.row { display: flex; flex-direction: row; }
.column { display: flex; flex-direction: column; }

.compact { flex-grow: 0; flex-shrink: 0; flex-basis: auto; }
.expand { flex-grow: 1; flex-shrink: 1; flex-basis: 0; }
```

These classes can be used to create just about any layout imaginable.
Occasionally, I’ll sprinkle in extra styles like `justify-content: center`,
`flex-wrap: wrap`, or `flex-grow: 4` to make small tweaks, but these are rarely
needed and easy to remember or lookup.

Check out this [Codepen](https://codepen.io/chipjacks/pen/XWjVQqd) for a bunch of examples:
<p class="codepen" data-height="870" data-theme-id="light" data-default-tab="result" data-user="chipjacks" data-slug-hash="XWjVQqd" style="height: 870px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;" data-pen-title="Four Line Layout">
  <span>See the Pen <a href="https://codepen.io/chipjacks/pen/XWjVQqd">
  Four Line Layout</a> by Chip Jackson (<a href="https://codepen.io/chipjacks">@chipjacks</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>

The beauty of this approach is its size and simplicity. Is this a row or a
column? Should it expand or stay compact? These are questions a kindergartener
could answer without needing to read a bunch of docs or import another
dependency.
