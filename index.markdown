---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: default
---
<div class="posts">
{% for post in site.posts %}
    <article class="post">
      <h2>{{ post.date | date: "%Y-%m-%d" }} - <a href="{{ site.baseurl }}{{ post.url }}">{{ post.title }}</a></h2>
      {% for category in post.categories %} <span class="category"> {{ category }}</span> {% endfor %}
      {% for tag in post.tags %} <span class="tag">#{{tag}}</span> {% endfor %}
      <div class="entry">{{ post.excerpt }}</div>
    </article>
    {% endfor %}
</div>
