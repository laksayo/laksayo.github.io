---
layout: default
title: "rambles"
permalink: /rambles/ # the permalink should match the page path
body_class: blog-page
description: "Just rambles. I go to events, sometimes in costume, sometimes behind a table, sometimes just looking around."
---
<section class="blog-header">
  <h1 class="blog-title">{{ page.title }}</h1>
  {% if page.description %}
    <p class="blog-description">{{ page.description }}</p>
  {% endif %}
</section>

<section id="blog-container">
  <div class="blog-grid">
    {% for post in site.posts %}
      <article class="blog-card">
        {% if post.featured_image %}
          <a href="{{ post.url | relative_url }}">
            <img src="{{ post.featured_image | relative_url }}" alt="{{ post.title }}">
          </a>
        {% endif %}
        <header>
          <h2><a href="{{ post.url | relative_url }}">{{ post.title }}</a></h2>
          <p class="post-date">{{ post.date | date: "%B %d, %Y" }}</p>
        </header>
        <section class="excerpt">
           <div class="excerpt-text">
            {{ post.excerpt | strip_html | truncatewords: 40 }}
          </div>
          <p><a href="{{ post.url | relative_url }}">Read more →</a></p>
        </section>
      </article>
    {% endfor %}
  </div>
</section>
