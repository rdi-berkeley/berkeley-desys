---
layout: blank
title: "Decentralized Systems"
permalink: /s22_syllabus
---

<table style="table-layout: fixed; font-size: 88%;">
  <thead>
    <tr>
      <th style="width: 10%;">Date</th>
      <th style="width: 50%;">Topic</th>
      <th style="width: 40%;">Recommended Reading</th>
    </tr>
  </thead>
  <tbody>
    {% for row in site.data.syllabus %}
      {% for lec in row.lectures %}
        <tr>
          <td>{{ lec.date }}</td>
          <td>{{ lec.topic.title }}
            <br>
            {% if lec.topic.speaker %}
              Speaker: {{ lec.topic.speaker }}
            {% endif %}
            {% if lec.topic.slides %}
              <ul style="margin-bottom: 0;">
                {% for s in lec.topic.slides %}
                  {% if s.file %}
                    <li><a target="_parent" href="./assets/material/{{ s.file }}" style="font-size: 100%;">Slides: {{ s.name }}</a></li>
                  {% else %}
                    <li><a target="_parent" href="{{ s.link }}" style="font-size: 80%;">Slides: {{ s.name }}</a></li>
                  {% endif %}
                {% endfor %}
              </ul>
            {% endif %}
          </td>
          <td>
            {% if lec.reading %}
              <ul style="margin-bottom: 0;">
                {% for r in lec.reading %}
                  {% if r.file %}
                    {% assign reading_link = './assets/material/' | append: r.file %}
                  {% endif %}
                  {% if r.link %}
                    {% assign reading_link = r.link %}
                  {% endif %}
                  <li><a target="_parent" href="{{ reading_link }}" style="font-size: 24px;">{{ r.name }}</a></li>
                {% endfor %}
              </ul>
            {% endif %}
          </td>
        </tr>
      {% endfor %}
    {% endfor %}
  </tbody>
</table>
