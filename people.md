---
title: People
permalink: /people/
---



<!--{% assign people_array = "pi|ap|postdoc|gradstudent|visiting|alumni" | split: "|" %}-->

{% assign people_sorted = (site.people | sort: 'joined' %}
{% assign people_array = "pi|adp|ap|gradstudent|visiting|alumni" | split: "|" %}

{% for item in people_array %}



<div class="pos_header">
{% if item == 'postdoc' %}
<h3>Postdoctoral Fellows</h3>
 {% elsif item == 'pi' %}
<h3>Director</h3> 
 {% elsif item == 'adp' %}
<h3>Adjunct Staffs</h3>
  {% elsif item == 'ap' %}

<h3>Postdoc Research Fellow</h3>
 {% elsif item == 'gradstudent' %}

<h3>Graduate Students</h3>
 {% elsif item == 'visiting' %}
<h3>Visiting Students</h3>
 --who stayed for more than 12 months 
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
