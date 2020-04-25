---
title: Categories

# All the Categories of posts
# v2.0
# https://github.com/cotes2020/jekyll-theme-chirpy
# © 2017-2019 Cotes Chung
# MIT License
---
{% assign sort_categories = site.categories | sort %}

{% for category in sort_categories %}
  {% assign category_name = category | first %}
  {% assign posts_of_category = category | last %}
  {% assign first_post = posts_of_category | first %}
  <p>{{ category_name }}</p>
  <div class="card categories">
    <!-- top-category -->
    <div class="card-header d-flex justify-content-between hide-border-bottom" id="h_{{ category_name }}">
      <span>
        <i class="far fa-folder fa-fw"></i>
        <a href="{{ site.baseurl }}/categories/{{ category_name | replace: ' ', '-' | downcase | url_encode }}/"
          class="ml-1 mr-2">{{ category_name }}</a>
        <!-- content count -->
        {% assign top_posts_size = site.categories[category_name] | size %}
        <span class="text-muted small font-weight-light">      
          {{ top_posts_size }}
          post{% if top_posts_size > 1 %}s{% endif %}
        </span>
      </span>
    </div> <!-- .card-header -->
  </div> <!-- .card -->
{% endfor %}
<script src="{{ site.baseurl }}/assets/js/dist/category-collapse.min.js" async></script>
