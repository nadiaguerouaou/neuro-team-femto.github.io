---
title: People
permalink: /people/
---

{% assign people_sorted = site.people | sort: 'joined' %}
{% assign role_array = "faculty|postdoc|phdstudent|visiting|others|alumni" | split: "|" %}

{% for role in role_array %}

{% assign people_in_role = people_sorted | where: 'position', role %}

<!-- Skip section if there's nobody -->
{% if people_in_role.size == 0 %}
  {% continue %}
{% endif %}

<div class="pos_header">
{% if role == 'postdoc' %}
<h3>Postdoctoral Fellows</h3>
 {% elsif role == 'faculty' %}
<h3>Permanent staff</h3>
 {% elsif role == 'phdstudent' %}
<h3>PhD Students</h3>
 {% elsif role == 'visiting' %}
<h3>Visiting Scholars</h3>
<!--  {% elsif role == 'alumni' %} 
<h3>Alumni</h3> -->
{% endif %}
</div>

{% if role != 'alumni' %}
<div class="content list people">
  {% for profile in people_sorted %}
    {% if profile.position contains role %}
      <div class="list-item-people">
        <p class="list-post-title">
          {% if profile.avatar %}
            <a href="{{ site.baseurl }}{{ profile.url }}"><img class="profile-thumbnail" src="{{site.baseurl}}/images/people/{{profile.avatar}}"></a>
          {% else %}
            <a href="{{ site.baseurl }}{{ profile.url }}"><img class="profile-thumbnail" src="http://evansheline.com/wp-content/uploads/2011/02/facebook-Storm-Trooper.jpg"></a>
          {% endif %}
          <a class="name" href="{{ site.baseurl }}{{ profile.url }}">{{ profile.name }}</a>
        </p>
      </div>    
    {% endif %}
  {% endfor %}
</div>
<hr>


{% endif %}
{% endfor %}


<div class="pos_header">
<h3>Alumni</h3>
</div>

<br>

| Who are they | When were they here | Where they went |
| :------------- |:-------------| :-----------|
| [Quentin Decultot](https://www.linkedin.com/in/quentin-décultot-b41b62202) | Master Student (2021) | Continuing studies at ENSMM, Besançon, FR |

Alumni members of the CREAM team (2014-2020), and where they went next, can be found on the [CREAM]({{site.baseurl}}/cream) history page .  
