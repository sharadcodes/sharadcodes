---
title: Categories
permalink: "/categories/"
layout: default
---

<div>
{% for category in site.categories %}
  <div class="archive-group">
    {% capture category_name %}{{ category | first }}{% endcapture %}
    <div id="#{{ category_name | slugize upcase }}"></div>
    <p></p>
    
    <h3 class="category-head" style="color:#2b2b2b;">{{ category_name | upcase  }}</h3>
    <a name="{{ category_name | slugize upcase }}"></a>
    {% for post in site.categories[category_name] %}
    <article class="archive-item">
      <h5><a href="{{ site.baseurl }}{{ post.url }}">{{post.title | capitalize}}</a></h5>
    </article>
    {% endfor %}
  </div>
{% endfor %}
</div>
