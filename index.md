---
layout: default
title: teconas
---
# teconas

Apps & games by teconas.

{% for game in site.games -%}
{%- assign base = game.slug | prepend: '/' | append: '/' -%}
## [{{ game.name }}]({{ base | relative_url }}){% if game.draft %} (draft){% endif %}

{{ game.description }}

- [More]({{ base | relative_url }})
- [Privacy Policy]({{ base | append: 'privacy/' | relative_url }})
{%- if game.play_store %}
- [Google Play]({{ game.play_store }})
{%- endif %}

{% endfor -%}

---

[Privacy Policy for this website]({{ '/privacy/' | relative_url }})
