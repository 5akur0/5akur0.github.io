---
layout: default     # 使用同样的 default 布局
title: Sakuro's Website | Photography  # 页面标题
---

## Film Photography Rolls

Here's a log of the film rolls I've shot and processed.

<div class="film-roll-list">
{% if site.data.films.size > 0 %} {# 检查是否有数据 #}
  {% for film_roll in site.data.films %} {# 遍历 _data/films.yml 里的每一项 #}
    <div class="film-roll-item">
      <h3>{{ film_roll.name | escape }} ({{ film_roll.format }}) {% if film_roll.pushed_to %}- Pushed to {{ film_roll.pushed_to }}{% endif %}</h3>
      <p><strong>Shot Date:</strong> {{ film_roll.shot_date }}</p>
      <p><strong>Notes:</strong> {{ film_roll.notes | escape }}</p>
      <p><strong>Development:</strong> {{ film_roll.develop_info | escape }}</p>
      <p><em>(Gallery links coming soon!)</em></p>
      {# 稍后可以加上照片数量和画廊链接 #}
      {# Example: <p>Contains {{ film_roll.photos | size }} photos. <a href="/gallery/{{ film_roll.id }}.html">View Gallery</a></p> #}
    </div>
  {% endfor %}
{% else %}
  <p>No film data found. Add entries to <code>_data/films.yml</code>.</p>
{% endif %}
</div>