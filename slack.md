---
title: Slack
nav-icon: /assets/slack-symbol.svg
students:
  savedSlackPassToLastPass:
    01: true
    02: true
    03: true
    04: true
    05: false
    06: true
    07: false
    08: false
    09: false
    10: false
    11: true
    12: false
    13: true
    14: true
    15: false
    16: false
    17: false
    18: false
    19: false
    20: true
    21: false
---

Have you saved your [CiMing2017.slack.com](https://ciming2017.slack.com) password in your LastPass vault?

<style>
  .student-tasks-grid span {
  display: inline-block;
  margin: 1em;
  padding: 0.3em;
  }
  .student-tasks-grid span.done {
  background-color: #2F8;
  }
  .student-tasks-grid span.yet-to-do {
  background-color: #F28;
  }
</style>

<div class="student-tasks-grid" style="display:flex-wrap;">
{% for student in page.students.savedSlackPassToLastPass %}
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

