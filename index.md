---
layout: default
---

<style>
  ul.post-list {

  }
  ul.post-list>li {
    display: inline-block;
    border: dotted 0.2em #444;
    border-radius: 0.4em;
    padding: 1em;
    max-width: 14em;
  }
  .link-list>li {
    box-sizing: border-box;
  }
</style>

<div class="home">
  <h1 class="page-heading">Links To Posts</h1>
  <ul class="post-list link-list">
    {% assign posts = site.posts | where:"categories","Spring" %}
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

  <p>take a look at <a href="{{ "/archive/" | prepend: site.baseurl }}">old posts</a></p>
