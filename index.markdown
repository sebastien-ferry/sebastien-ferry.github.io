---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: default
---
<div class="posts">
{% for post in site.posts %}
    <article class="post" style="background-color:rgb(
    {{ post.date | date: "%Y" |minus:2010 |times:8 }},
    {{ post.date | date: "%Y" |minus:2010 |times:10 |plus: 100}},
    {{ post.date | date: "%Y" |minus:2010 |times:10 |plus: 100}},
    {{ post.date | date: "%Y" |minus:2010 |times:10 |plus: 100}}
    );">
    
<span style="font-size:13px; float:right; border:1px solid red; border-radius:5px; padding:0em 0em 0em 0em;"><b>{{ post.date | date: "%Y" }}</b>
<span style="font-size:11px;">{{ post.date | date: "%m" }}</span><span style="font-size:7px;">-{{ post.date | date: "%d" }}</span>
</span>
      <h1><a href="{{ site.baseurl }}{{ post.url }}">{{ post.title }}</a></h1>&nbsp;{% for category in post.categories %} <span class="category" style="text-align:right;"> {{ category }}</span> {% endfor %} {% for tag in post.tags %} <span class="tag" style="text-align:right;">#{{tag}}</span> {% endfor %}
      <div class="entry">
      {{ post.excerpt }}
      </div>
    </article>
    {% endfor %}
</div>
