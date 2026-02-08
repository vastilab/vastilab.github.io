---
title: People
permalink: /people/
---



{% assign people_sorted = (site.people | sort: 'joined' %}
{% assign people_array = "pi|gradstudent|alumni" | split: "|" %}

{% for item in people_array %}



<div class="pos_header">
{% if item == 'pi' %}
<h3>Founder</h3>
 {% elsif item == 'gradstudent' %}
<h3>Team Member</h3>
 {% elsif item == 'alumni' %}
<h3>Alumni</h3>
{% endif %}
</div>

<div class="content list people">
  {% for profile in people_sorted %}
    {% if profile.position contains item %}
    <div class="list-item-people">
      <p class="list-post-title">
        {% if profile.avatar %}
            {% if profile.position == "pi" %}
                <a href="{{ site.baseurl }}{{ profile.url }}"><img width="285" height="214" src="{{site.baseurl}}/images/people/{{profile.avatar}}"></a>
            {% else %}
                                <a href="{{ site.baseurl }}{{ profile.url }}"><img height="214" style="width: auto;" src="{{site.baseurl}}/images/people/{{profile.avatar}}"></a>
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
