---
title: People
permalink: /people/
---

{% assign people_sorted = site.people | sort: 'joined' %}
{% assign people_array = "pi|gradstudent|alumni" | split: "|" %}

{% for item in people_array %}
<section class="people-section people-section-{{ item }}">

  <div class="pos_header">
    {% if item == 'pi' %}
      <h3>Founder</h3>
    {% elsif item == 'gradstudent' %}
      <h3>Team Member</h3>
    {% elsif item == 'alumni' %}
      <h3>Alumni</h3>
    {% endif %}
  </div>

  <div class="content list people people-grid">
    {% for profile in people_sorted %}
      {% if profile.position contains item %}
        <div class="list-item-people">
          {% if profile.avatar %}
            <a href="{{ site.baseurl }}{{ profile.url }}" class="avatar-box">
              <img class="avatar-img"
                   src="{{ site.baseurl }}/images/people/{{ profile.avatar }}"
                   alt="{{ profile.name }}"
                   loading="lazy">
            </a>
          {% else %}
            <a href="{{ site.baseurl }}{{ profile.url }}" class="avatar-box">
              <img class="avatar-img"
                   src="http://evansheline.com/wp-content/uploads/2011/02/facebook-Storm-Trooper.jpg"
                   alt="{{ profile.name }}"
                   loading="lazy">
            </a>
          {% endif %}

          <a class="name" href="{{ site.baseurl }}{{ profile.url }}">{{ profile.name }}</a>
        </div>
      {% endif %}
    {% endfor %}
  </div>

</section>
{% endfor %}

