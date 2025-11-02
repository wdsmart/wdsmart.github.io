---
permalink: /teaching/
title: Teaching
---

At Oregon State, I mostly teach classes in [Robotics](https://robotics.oregonstate.edu) and related areas, although I sometimes also teach classes in [Mechanical Engineering](https://engineering.oregonstate.edu/MIME).  You can find the classes that I'm currently teaching in the [OSU class catalog](https://classes.oregonstate.edu/?keyword=William%20Smart).  Before coming to OSU in 2012, I was on the faculty at [Washington University in St. Louis](https://wustl.edu), where I mostly taught classes in [Computer Science](https://cse.wustl.edu).

{% assign subject_ordering ='ROB ME ENGR HC CSE EN' | split: ' ' %}

<dl>
  {% for subject in subject_ordering %}
    {% if subject == 'CSE' %}
      <h2>Taught at Washington University</h2>
    {% endif %}

    {% assign class_list = site.data.classes | where: 'subject', subject | sort: 'number' %}

      {% for class in class_list %}
        <dt><b>{{ class.subject }} {{ class.number }}: {{ class.title }}</b></dt>
        <dd>
          {{ class.informal }}
          {% include instance-detail.md subject=class.subject number=class.number %}
        </dd>
      {% endfor %}
  {% endfor %}
</dl>
