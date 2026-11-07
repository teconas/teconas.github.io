---
layout: default
lang: de
title: teconas
---
# teconas

Apps & Spiele von teconas.

{% for game in site.games -%}
{%- assign base = game.slug | prepend: '/' | append: '/' -%}
## [{{ game.name }}]({{ base | relative_url }}){% if game.draft %} (Entwurf){% endif %}

{{ game.description }}

- [Mehr / More]({{ base | relative_url }})
- [Datenschutzerklärung / Privacy Policy]({{ base | append: 'privacy/' | relative_url }})
{%- if game.play_store %}
- [Google Play]({{ game.play_store }})
{%- endif %}

{% endfor -%}
