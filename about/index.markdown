---
layout: about
title: "About"
description: "Learn more about me, my background, skills, and experience in software development."
---

<style>
.profile-image-container {
  position: relative;
  display: inline-block;
  width: 40%;
  float: right;
  margin: 10px;
  overflow: hidden;
}

@media (max-width: 500px) {
  .profile-image-container {
    width: 90%;
    margin: 0 auto 10px auto;
    max-width: 250px;
    float: none;
    display: block;
  }
}

.profile-image-container img {
  display: block;
  width: 100%;
  height: auto;
  border-radius: 10px;
}

.profile-image-base {
  position: relative;
}

.profile-image-overlay {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  opacity: 0;
  transition: opacity 0.5s ease-in-out;
}

.profile-image-container:hover .profile-image-overlay,
.profile-image-container.scrolled .profile-image-overlay {
  opacity: 1;
}
</style>

<div class="profile-image-container">
  <img class="profile-image-base" src="/images/mba_profile_square.jpg" alt="Photo of Chip Jackson" />
  <img class="profile-image-overlay" src="/images/mba_profile_smiling_square.jpg" alt="Photo of Chip Jackson smiling" />
</div>

<script>
(function() {
  const container = document.querySelector('.profile-image-container');
  let hasScrolled = false;
  
  function handleScroll() {
    if (!hasScrolled && window.scrollY > 100) {
      hasScrolled = true;
      container.classList.add('scrolled');
    }
  }
  
  window.addEventListener('scroll', handleScroll);
})();
</script>

Hi, I'm Chip. Thanks for checking out my website! I hope you have found
something here interesting or useful.

Most of my career has been spent in data engineer roles, building pipelines to
extract, clean, transform, and move large amounts
of data. In the past I've focused on web crawl and extraction of structured
data, while currently I'm working on streaming pipelines primarily used for
sending job recommendation emails at ZipRecruiter. I find there's a seemingly
unlimited supply of messy and disorganized data available in the the digital
realm, so there's tremendous value that can be unlocked if one can effectively
wrangle it. Yee haw!

Outside of my day job, I see myself as a bit of a generalist. I enjoy exploring
new topics, broadening my skillsets, and building small apps and games. I've
designed and developed web apps, mobile apps, browser extensions, frontend
components, and backend libraries. I got my degrees in Math, Computer Science,
Physics, and Business and enjoy reading history, business, biographies, and
adventure books.

#### Connect

<div style="margin-left: 10px; margin-top: 10px;">
<div style="display:flex; flex-direction: row; gap: 10px; align-items: center;">
<svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" fill="currentColor" class="bi bi-linkedin" viewBox="0 0 16 16">
  <path d="M0 1.146C0 .513.526 0 1.175 0h13.65C15.474 0 16 .513 16 1.146v13.708c0 .633-.526 1.146-1.175 1.146H1.175C.526 16 0 15.487 0 14.854zm4.943 12.248V6.169H2.542v7.225zm-1.2-8.212c.837 0 1.358-.554 1.358-1.248-.015-.709-.52-1.248-1.342-1.248S2.4 3.226 2.4 3.934c0 .694.521 1.248 1.327 1.248zm4.908 8.212V9.359c0-.216.016-.432.08-.586.173-.431.568-.878 1.232-.878.869 0 1.216.662 1.216 1.634v3.865h2.401V9.25c0-2.22-1.184-3.252-2.764-3.252-1.274 0-1.845.7-2.165 1.193v.025h-.016l.016-.025V6.169h-2.4c.03.678 0 7.225 0 7.225z"/>
</svg>
<a href="http://www.linkedin.com/pub/chip-jackson/66/967/675/">LinkedIn</a>
</div>

<div style="display:flex; flex-direction: row; gap: 10px; align-items: center;">
<svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" fill="currentColor" class="bi bi-github" viewBox="0 0 16 16">
<path d="M8 0C3.58 0 0 3.58 0 8c0 3.54 2.29 6.53 5.47 7.59.4.07.55-.17.55-.38 0-.19-.01-.82-.01-1.49-2.01.37-2.53-.49-2.69-.94-.09-.23-.48-.94-.82-1.13-.28-.15-.68-.52-.01-.53.63-.01 1.08.58 1.23.82.72 1.21 1.87.87 2.33.66.07-.52.28-.87.51-1.07-1.78-.2-3.64-.89-3.64-3.95 0-.87.31-1.59.82-2.15-.08-.2-.36-1.02.08-2.12 0 0 .67-.21 2.2.82.64-.18 1.32-.27 2-.27s1.36.09 2 .27c1.53-1.04 2.2-.82 2.2-.82.44 1.1.16 1.92.08 2.12.51.56.82 1.27.82 2.15 0 3.07-1.87 3.75-3.65 3.95.29.25.54.73.54 1.48 0 1.07-.01 1.93-.01 2.2 0 .21.15.46.55.38A8.01 8.01 0 0 0 16 8c0-4.42-3.58-8-8-8"/>
</svg>
<a href="https://github.com/chipjacks">Github</a>
</div>

</div>
