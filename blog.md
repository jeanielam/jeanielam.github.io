---
layout: archive
permalink: /blog/
title: "Latest Posts"
paginate: true
---

<div class="tiles">
	{% for post in paginator.posts %}
		{% include post-grid.html %}
	{% endfor %}
</div>

<div class="pagination">
  <ul>
    {% if paginator.previous_page %}
      {% if paginator.previous_page == 1 %}
        <li>
          <a href="/blog/">&laquo;</a>
        </li>
      {% else %}
        <li>
          <a href="/blog/{{paginator.previous_page}}">&laquo;</a>
        </li>
      {% endif %}
    {% else %}
      <li class="disabled">
        <a href="#">&laquo;</a>
      </li>
    {% endif %}
    {% if paginator.page == 1 %}
      <li class="active">
        <a href="#">1</a>
      </li>
    {% else %}
      <li>
        <a href="/blog/">1</a>
      </li>
    {% endif %}
    {% for count in (2..paginator.total_pages) %}
      {% if count == paginator.page %}
        <li class="active">
          <a href="#">{{count}}</a>
        </li>
      {% else %}
        <li>
          <a href="/blog/{{count}}">{{count}}</a>
        </li>
      {% endif %}
    {% endfor %}
    {% if paginator.next_page %}
      <li>
        <a href="/blog/{{paginator.next_page}}">&raquo;</a>
      </li>
    {% else %}
      <li class="disabled">
        <a href="#">&raquo;</a>
      </li>
    {% endif %}
  </ul>
</div>