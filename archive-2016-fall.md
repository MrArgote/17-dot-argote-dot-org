---
layout: default
---

<style>
  ul.post-list>li {
    border: dotted 0.2em #444;
    padding: 1em; }
  .link-list>li {
    box-sizing: border-box; }
</style>

<div class="home">
  <h1 class="page-heading">Links To Posts</h1>
  <ul class="post-list link-list">
    {% assign posts = site.posts | where:"categories","Fall" %}
    {% for post in posts %}
      <li>
        <span class="post-meta">{{ post.date | date: "%b %-d, %Y" }}</span>
        <h2>
          <a class="post-link" href="{{ post.url | prepend: site.baseurl }}">
            {{ post.title | escape }}
          </a>
        </h2>
        <span>
          {{ post.excerpt }}
        </span>
      </li>
    {% endfor %}
  </ul>
</div>

<p>take a look at
  <a href="{{ "/" | prepend: site.baseurl }}">
    current posts
  </a>
</p>
