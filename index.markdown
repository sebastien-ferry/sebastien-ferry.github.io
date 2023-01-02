---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: default
---
<div class="posts">
{% assign current_year = 0 %}
{% for post in site.posts %}
    {% assign year = post.date | date: "%Y" %}

{% if current_year != year %}
    {% assign current_year = year %}
</div>
<h1> {{ year }} </h1>
<div class="posts">
{% endif %}

{% if post.tags[0] == "WIP" %}
    <article class="post" style="background-color:rgb(176, 177, 78);">
{% else %}
    <article class="post" style="background-color:rgb(
    {{ post.date | date: "%Y" |minus:2010 |times:8 }},
    {{ post.date | date: "%Y" |minus:2010 |times:10 |plus: 100}},
    {{ post.date | date: "%Y" |minus:2010 |times:10 |plus: 100}},
    {{ post.date | date: "%Y" |minus:2010 |times:10 |plus: 100}}
    );">
{% endif %}
<a href="{{ site.baseurl }}{{ post.url }}">

<span style="font-size:13px; float:right; padding:0.3em 0em 0em 0em;">{{ post.date | date: "%Y" }}
<b><span style="font-size:11px;">{{ post.date | date: "%m" }}</span><span style="font-size:7px;">-{{ post.date | date: "%d" }}</span></b>
</span>
      <h2>{{ post.title }}</h2>&nbsp;{% for category in post.categories %} <span class="category" style="text-align:right;"> {{ category }}</span> {% endfor %} {% for tag in post.tags %} <span class="tag" style="text-align:right;">#{{tag}}</span> {% endfor %}
      <div class="entry">
      {{ post.excerpt }}
      </div>
</a>
    </article>
    {% endfor %}
</div>
