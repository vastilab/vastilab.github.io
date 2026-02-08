---
title: People
permalink: /people/
---

{% assign people_sorted = site.people | sort: 'joined' %}
{% assign people_groups = "pi|team" | split: "|" %}

{% for group in people_groups %}

<div class="pos_header">
  {% if group == 'pi' %}
    <h3>Founder</h3>
  {% else %}
    <h3>Team Member</h3>
  {% endif %}
</div>

<div class="content list people">
  {% for profile in people_sorted %}

    {% assign is_pi = false %}
    {% if profile.position contains 'pi' %}
      {% assign is_pi = true %}
    {% endif %}

    {% if (group == 'pi' and is_pi == true) or (group == 'team' and is_pi == false) %}

    {% assign profile_url = profile.url | relative_url %}

    {% if profile.avatar %}
      {% assign avatar_src = '/images/people/' | append: profile.avatar | relative_url %}
    {% else %}
      {% assign avatar_src = 'https://www.gravatar.com/avatar/?d=mp&s=400' %}
    {% endif %}

    <div class="list-item-people">
      <p class="list-post-title">
        {% if is_pi %}
          <a href="{{ profile_url }}">
            <img
              width="160"
              height="204"
              loading="lazy"
              decoding="async"
              style="object-fit: cover; object-position: center;"
              src="{{ avatar_src }}"
              alt="{{ profile.name | escape }}">
          </a>
        {% else %}
          <a href="{{ profile_url }}">
            <img
              width="130"
              height="166"
              loading="lazy"
              decoding="async"
              style="object-fit: cover; object-position: center;"
              src="{{ avatar_src }}"
              alt="{{ profile.name | escape }}">
          </a>
        {% endif %}

        <a class="name" href="{{ profile_url }}">{{ profile.name }}</a>
      </p>
    </div>

    {% endif %}
  {% endfor %}
</div>

{% endfor %}
