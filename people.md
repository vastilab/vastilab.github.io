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
    
    <div class="list-item-people">
      <p class="list-post-title">
        {% if profile.avatar %}
            {% if is_pi %}
                <a href="{{ site.baseurl }}{{ profile.url }}"><img width="160" height="204" src="{{site.baseurl}}/images/people/{{profile.avatar}}"></a>
            {% else %}
                <a href="{{ site.baseurl }}{{ profile.url }}"><img width="130" height="166" src="{{site.baseurl}}/images/people/{{profile.avatar}}"></a>
            {% endif %}
        {% else %}
            <a href="{{ site.baseurl }}{{ profile.url }}"><img width="200" src="http://evansheline.com/wp-content/uploads/2011/02/facebook-Storm-Trooper.jpg"></a>
        {% endif %}
        <a class="name" href="{{ site.baseurl }}{{ profile.url }}">{{ profile.name }}</a>
      </p>
    </div>    
    {% endif %}
  {% endfor %}
</div>
{% endfor %}
