---
layout: post
title: "Runo Towers"
date: 2025-09-24
snippet: "A Tetris-like mobile game, where blocks are generated based on miles you've run."
categories: posts
---

<div style="display: flex; margin: 20px 0; flex-wrap: wrap; justify-content: center">
    <img src="/images/runo_towers_sign_in.png" alt="Runo Towers Sign In" style="max-height: 500px; margin-right: 20px" />
    <img src="/images/runo_towers_new_game.png" alt="Runo Towers New Game" style="max-height: 500px; margin-right: 20px" />
    <img src="/images/runo_towers_tutorial.png" alt="Runo Towers Tutorial" style="max-height: 500px; margin-right: 20px" />
    <img src="/images/runo_towers_demo.gif" alt="Runo Towers Demo" style="max-height: 500px; margin-right: 20px" />
</div>
For years I've been interested in mobile development, but never quite had
the head-space to build a native app, instead opting to build web applications
that work well on mobile devices as well. This all changed when I stumbled
across [Expo](https://expo.dev/), a framework for building React Native apps, and something just
clicked for me. It made it super-easy to get started and I enjoyed being able to
preview my apps in a web browser without having to start up a simulator or
connect a mobile device to run them. Getting to leverage all my existing web
development and React skills was a huge win.

Somewhat on a whim, I decided to build a Tetris-like app for runners. Connect
your Strava account and earn a block for each mile you run. Stack the blocks to
build towers and compete with your friends. I started the app on a vacation in
2024, thinking it would just be a quick/fun project for a few weeks. A few
months later I found myself struggling to integrate [Matter.js](https://github.com/liabru/matter-js), a 2D physics
engine, determined to take the app to the next level. On my next long vacation
(over a year later 😅) I'm putting the finishing touches on the app.

Needless to say, it turned into a much bigger project than I had anticipated.
There were lots of difficult learnings along the way and jumping into coding without
doing any design or planning made the development process a bit more windy and
slow. AI coding agents played a large role in the app development, from a
toy-like ChatGPT 3/4 generating some of the initial code for the Tetris
mechanics, to more recently, powerful Claude agents seamlessly implementing
entire features across the full stack.

My mind feels much lighter having this one shipped, but I'm already scheming for
my next big project. Runo Towers does a good job differentiating from other
apps already on the market, targeting a niche group of runners with a casual
game-like experience, but based on the feedback so far it's not something that
anyone really feels a need for in their life 🙃. Next time, I'll want to do a
better job of prototyping and gather user-feedback early, before investing a ton
of time coding. I've also leveled-up my skills by taking some
[LangChain/LangGraph](https://www.langchain.com/) courses, with the hopes of identifying new and powerful
integration points for LLMs in my future projects. For now though, I'll just
be focusing on keeping my latest Topply Tower at the top of the Runo Towers high
score board 🏆

#### 👉 [Download Runo Towers](https://runo.app/runo-towers/)
