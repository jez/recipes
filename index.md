---
vim: ft=liquid tw=90 fo-=tc
# liquid_subtype=pandoc
layout: 'index'
title: 'Recipes – Jake Zimmerman'
subtitle: 'Where I collect recipes I’ve made, so that I can refer back to them
and share them.<br>Most of these are not my own recipes.'
# Always regenerate, even with --incremental
regenerate: true
---

{% capture numrecipes %}{{ site.recipes | size }}{% endcapture %}
{% if numrecipes != '0' %}
  {% assign pinned_recipes = site.recipes | where: "pinned", true %}
  {% capture num_pinned_recipes %}{{ pinned_recipes | size }}{% endcapture %}
  {% if num_pinned_recipes != '0' %}

# Suggested recipes

{% for recipe in pinned_recipes -%}
### {{ recipe.title }}

{{ recipe.description }}\
_[Read more →]({{ recipe.url }})_

{% endfor %}
{% endif %}

{% comment %}
# Categories

→ [Posts by category](categories/)

# All recipes
{% endcomment %}

{% for recipe in site.recipes %}
- [{% if recipe.draft %}[DRAFT] {% endif %}{{ recipe.title }}]({{ site.baseurl }}{{ recipe.url }})
{% endfor %}
{% else %}

# All recipes

- *None to show.*
{% endif %}
