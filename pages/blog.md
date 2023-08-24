---
layout: page
title: Blog
permalink: /blog/
feature-img: assets/img/img3.jpg
---

<div class=coll2>
<h2>Math Posts</h2>
<ul>
  {% for post in site.posts %}
  	{% if post.categories contains 'mathematics' %}
        
	      <h3><a href="{{ post.url }}">{{ post.title }}</a> </h3> 
          <b><i> {{ post.date | date: "%B %-d, %Y" }} </i></b> <!-- - {{ post.author }}  -->
          <p> {{ post.excerpt | strip_html | truncate:150 }} </p>
        {% capture tag_list %}{{ post.tags | join: "|"}}{% endcapture %}
        {% include default/tags_list.liquid tags=tag_list %}
	    
    {% endif %}   <!-- cat-match-p -->
  {% endfor %}
</ul>
</div>


<div class=coll2>
<h2>non-math Posts</h2>
<ul>
  {% for post in site.posts %}
  {% unless post.categories contains 'mathematics' %}
     <h3><a href="{{ post.url }}">{{ post.title }}</a> </h3> 
      <b><i> {{ post.date | date: "%B %-d, %Y" }} </i></b> <!-- - {{ post.author }}  -->
      <p> {{ post.excerpt | strip_html | truncate:150 }} </p>
      {% capture tag_list %}{{ post.tags | join: "|"}}{% endcapture %}
      {% include default/tags_list.liquid tags=tag_list %}
  {% endunless %}
  {% endfor %}
</ul>
</div>



<style>
    .coll2 {
        float: left;
        width: 48%;
        padding-bottom: 50px;
    }
    @media screen and (max-width: 800px) { 
    .coll2 {
        float: left;
        width: 100%;
        padding-bottom: 50px;
    }
    }
    /* Clear floats after the columns */
    .roww:after {
        content: "";
        display: table;
        clear: both;
    }
</style>
