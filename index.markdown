---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: default
---
<div class="posts">
{% for post in site.posts %}
    <article class="post">
      <h1><a href="{{ site.baseurl }}{{ post.url }}">
      <span style="font-size:13px; float:right; border:1px solid red;border-radius: 5px;padding:0.25em 0.2em 0em 0.2em;">📅 <b>{{ post.date | date: "%Y" }}</b> <span style="font-size:10px;">{{ post.date | date: "%m" }}</span><span style="font-size:8px;">-{{ post.date | date: "%d" }}</span></span>
      {{ post.title }}</a> &nbsp;{% for category in post.categories %} <span class="category" style="text-align:right;"> {{ category }}</span> {% endfor %} {% for tag in post.tags %} <span class="tag" style="text-align:right;">#{{tag}}</span> {% endfor %} </h1>
      <div class="entry">
      {{ post.excerpt }}
      </div>
    </article>
    {% endfor %}
</div>
