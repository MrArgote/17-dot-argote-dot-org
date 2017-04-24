---
layout: default
---

<style>
  ul.post-list {

  }
  ul.post-list>ul>li {
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
    {% assign posts = site.posts | where:"categories","Act-II" | where:"categories","Spring" %}
    {% for post in posts %}
      {% assign currentdate = post.date | date: "%a, %B %d, %Y" %}
      {% if currentdate != date %}
      {% unless forloop.first %}</ul>{% endunless %}
      <h1>{{ currentdate | date: "%a %b %d" }}</h1>
      <ul>
      {% assign date = currentdate %}
      {% endif %}
      <li>
        <span class="post-meta">{{ post.date | date: "%b %-d, %Y" }}</span>
        <h2>
          <a class="post-link" href="{{ post.url | prepend: site.baseurl }}">
            {{ post.title | escape }}
          </a>
        </h2>
      </li>
      {% if forloop.last %}</ul>{% endif %}
    {% endfor %}
  </ul>
</div>

  <p>take a look at <a href="{{ "/archive-2017-spring-act-i/" | prepend: site.baseurl }}">old posts</a></p>
