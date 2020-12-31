---
layout: post
title:  "Four Line Layout"
date:   2020-12-29
snippet: "Define any layout with just four simple CSS classes."
categories: posts
---

Feeling both overwhelmed by all the CSS layout systems available now and
inspired by the simplicity of
[elm-ui's](https://package.elm-lang.org/packages/mdgriffith/elm-ui/1.1.8/Element#row)
use of just rows and columns, I created four CSS classes that provide a small
abstraction over
[`flexbox`](https://css-tricks.com/snippets/css/a-guide-to-flexbox/):

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

Check out this [Codepen](https://codepen.io/chipjacks/pen/XWjVQqd) for a bunch
of examples. Since it's all built on flexbox, everything responds nicely when the
viewport size or zoom changes.

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
