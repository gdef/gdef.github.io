---
layout: default
title: Questions
permalink: /questions/
---

Your {{ page.title }}
===

<div id="table-of-contents">
  <h3>Table of contents</h3>

  {% for item in site.data.questions %}
    {% assign: t-index = forloop.index %}
    <ul class="topic">
      <li>
        <a href="#{{ forloop.index }}">{{ forloop.index }}. {{ item.topic }}</a>

        <ul>
          {% for question in item.questions %}
            <li class="q">
              <a href="#{{ t-index }}-{{ forloop.index }}">{{ forloop.index }}. {{ question.q }}
              </a>

            </li>
          {% endfor %}
        </ul>
      </li>
    </ul>
  {% endfor %}
</div>

<div class="your-questions">

  <article>
    {% for item in site.data.questions %}
      {% assign: t-index = forloop.index %}

      <div class="topic">
        <h3 id="{{ forloop.index }}">{{ item.topic | upcase }}
        </h3>

        {% for question in item.questions %}
          <h4 class="question" id="{{ t-index }}-{{ forloop.index }}">
            {{ question.q }}

          </h4>

          <p class="a">{{ question.a | newline_to_br }}</p>

        {% endfor %}
      </div>
    {% endfor %}
  </article>
</div>

<div id="back-to-menu"><a href="#table-of-contents">&#9650;</a></div>