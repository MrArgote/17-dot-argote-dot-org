---
title: Points
nav-icon: /assets/four-dots.svg
---

<style>
  .student-tasks-grid span {
    display: inline-block;
    border-radius: 1em;
    padding: 0.3em; }
  .student-tasks-grid span.done {
    background-color: #2F8; }
  .student-tasks-grid span.done .number {
    background-color: #EEE; }
  .student-tasks-grid span.yet-to-do {
    background-color: #F4A; }
  .student-tasks-grid span.yet-to-do .number {
    background-color: #EEE; }
  .student-tasks-grid .number {
    border-radius: 10em;
    padding: 0.7em;
    display: inline-block; }
  .student-tasks-grid .done .number {
    color: #404 ;
    background-color: #fbf; }
  .student-tasks-grid .yet-to-do .number {
    color: #0FC ;
    background-color: #F65; }
</style>

<div class="student-tasks-grid" style="display:flex-wrap;">
{% for student in site.data.whowho.students %}
  <span>
  {% if student[1] %}
    <span class="done">
      <span class="number">
      {{ student[0] }}
      </span>
      <div>
      <div> {{ student[1].enname }} </div>
      <div> {{ student[1].snum }} </div>
      <div> {{ student[1].zhname }} </div>
      <div> {{ student[1].pyname }} </div>
      <div> {% if student[1].slacksn[0] %}@{% endif %}{{ student[1].slacksn[0] }} </div>
      <div> {{ student[1].email[0] }} </div>
      </div>
    </span>
  {% else %}
    <span class="yet-to-do">
      <span class="number">
      {{ student[0] }}
      </span>
      Not ready?
    </span>
  {% endif %}
  </span>
{% endfor %}
</div>

{% comment %}

Emptied Dropbox?

<div class="student-tasks-grid" style="display:flex-wrap;">
{% for student in site.data.emptiedDropbox.students %}
  <span>
  {% if student[1] %}
    <span class="done">
      <span class="number">
      {{ student[0] }}
      </span>
      Done
    </span>
  {% else %}
    <span class="yet-to-do">
      <span class="number">
      {{ student[0] }}
      </span>
      Not ready?
    </span>
  {% endif %}
  </span>
{% endfor %}
</div>


Lastpass?

<div class="student-tasks-grid" style="display:flex-wrap;">
{% for student in site.data.savedSlackPassToLastpass.students %}
  <span>
  {% if student[1] %}
    <span class="done">
      {{ student[0] }}
      Done
    </span>
  {% else %}
    <span class="yet-to-do">
      {{ student[0] }}
      Not ready?
    </span>
  {% endif %}
  </span>
{% endfor %}
</div>


{% endcomment %}

## Textbook

<div class="student-tasks-grid" style="display:flex-wrap;">
  {% for student in site.data.textbookWork.students %}

    {% assign pagesDone = 0 %}
      {% for unit in student[1].completed %}
          {% assign pagesDone = pagesDone | plus: unit[1].size %}
      {% endfor %}

    <div class="
      {% if pagesDone > 1 %} done
        {% else %} yet-to-do
      {% endif %}
    ">

      <div class="number"> {{ student[0] }} </div>

      <div> {% if student[1].comment != empty %}
        notes: {{ student[1].comment }}
      {% endif %} </div>

      {% for unit in student[1].completed %}
        {% if unit != empty %}
          <div>
            unit {{ unit[0] }} : page {{ unit[1] | join: ', ' }}
          </div>
        {% endif %}
      {% endfor %}

    </div>
    total: {{ pagesDone }}
  {% endfor %}
</div>

# Slack Responses

<div class="student-tasks-grid" style="display:flex-wrap;">
  {% for student in site.data.SlackResponses.students %}
    <span class="done">
      <span class="number">
        {{ student[0] }}
      </span>
      <span class="done">
        <div> biro = {{ student[1].biro }} </div>
        <div> budgies = {{ student[1].budgies }} </div>
        <div> superblocks = {{ student[1].superblocks }} </div>
        <div> spectacles = {{ student[1].spectacles }} </div>
        <div> moon = {{ student[1].road-moon }} </div>
        <div> lettuce = {{ student[1].regrow-lettuce }} </div>
        <div> roommates = {{ student[1].unusual-roommates }} </div>
        <div> introductions = {{ student[1].self-introductions }} </div>
      </span>
    </span>
  {% endfor %}
</div>


{% comment %}

Saved Dropbox password to Lastpass?

<div class="student-tasks-grid" style="display:flex-wrap;">
{% for student in site.data.savedDropboxToLastpass.students %}
  <span>
  {% if student[1] %}
    <span class="done">
      <span class="number">
      {{ student[0] }}
      </span>
      Done
    </span>
  {% else %}
    <span class="yet-to-do">
      <span class="number">
      {{ student[0] }}
      </span>
      Not ready?
    </span>
  {% endif %}
  </span>
{% endfor %}
</div>

{% endcomment %}

