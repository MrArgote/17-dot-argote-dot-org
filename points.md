---
title: Points
header-nav: false
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

  .student-tasks-grid tr td {
      background-color: #fff;
      text-align: center; }
  .student-tasks-grid tr:nth-child(even) td:nth-child(odd),
  .student-tasks-grid tr:nth-child(odd) td:nth-child(even) {
    background-color: #ccc; }
</style>

<h1>Points for Act I</h1>

<div class="student-tasks-grid" style="display:flex-wrap;">
  <span>
    <span class="done">
      <table>
        <tr>
          <th> </th>
          <th>name</th>
          <th>##</th>
          <th>名詞</th>
          <th>拼音</th>
          <th>slack handle</th>
          <th>e-mail</th>
        </tr>
        {% for student in site.data.whowho.students %}
          <tr>
            <td> <span class="number"> {{ student[0] }} </span> </td>
            <td> {{ student[1].enname }} </td>
            <td> {{ student[1].snum }} </td>
            <td> {{ student[1].zhname }} </td>
            <td> {{ student[1].pyname }} </td>
            <td> {% if student[1].slacksn[0] %}@{% endif %}{{ student[1].slacksn[0] }} </td>
            <td> {{ student[1].email[0] }} </td>
          </tr>
        {% endfor %}
      </table>
    </span>
  </span>
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

      <table>
        <tr style="background-color: #DCC;">
          <th style="margin: 1em;">unit</th>
          <th>page(s)</th>
        </tr>
        {% for unit in student[1].completed %}
          {% if unit[1] != empty %}
                <tr>
                  <td>{{ unit[0] }}</td>
                  <td>{{ unit[1] | join: ', ' }}</td>
                </tr>
          {% endif %}
        {% endfor %}
        <td style="background-color: #DCC;">
          total: {{ pagesDone }}
        </td>
      </table>

    </div>
  {% endfor %}
</div>

## Slack Responses


<div class="student-tasks-grid" style="display:flex-wrap;">
  <span class="done">
    <table>
      <tr>
        <td> seat # </td>
        <td>biro</td>
        <td>budgies</td>
        <td>superblocks</td>
        <td>spectacles</td>
        <td>moon</td>
        <td>lettuce</td>
        <td>roommates</td>
        <td>introductions</td>
      </tr>
      {% for student in site.data.SlackResponses.students %}
        <tr>
          <td> <span class="number"> {{ student[0] }} </span> </td>
          <td> <div> {{ student[1].biro }} </div> </td>
          <td> <div> {{ student[1].budgies }} </div> </td>
          <td> <div> {{ student[1].superblocks }} </div> </td>
          <td> <div> {{ student[1].spectacles }} </div> </td>
          <td> <div> {{ student[1].road-moon }} </div> </td>
          <td> <div> {{ student[1].regrow-lettuce }} </div> </td>
          <td> <div> {{ student[1].unusual-roommates }} </div> </td>
          <td> <div> {{ student[1].self-introductions }} </div> </td>
        </tr>
      {% endfor %}
    </table>
  </span>
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

