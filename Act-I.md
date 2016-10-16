---
layout: default
title: Act I
nav-icon: /assets/one.svg
---



<div class="home">
  <h1 class="page-heading">Full Posts</h1>
  <ul class="post-list">
    {% for post in site.posts %}
      <li>
        <span class="post-meta">{{ post.date | date: "%b %-d, %Y" }}</span>
        <h2>
          <a class="post-link" href="{{ post.url | prepend: site.baseurl }}">
            {{ post.title | escape }}
          </a>
        </h2>
        <span>
          {{ post.content }}
        </span>
      </li>
    {% endfor %}
  </ul>
</div>
