---
layout: default
---
{% for game in site.games -%}
{%- assign base = game.slug | prepend: '/' | append: '/' -%}
## [{{ game.name }}]({{ base | relative_url }}){% if game.draft %} (draft){% endif %}

{{ game.description }}

[Privacy Policy]({{ base | append: 'privacy/' | relative_url }})
{%- if game.play_store %} · [Google Play]({{ game.play_store }}){% endif %}

{% endfor -%}
