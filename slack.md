---
title: Slack
nav-icon: /assets/slack-symbol.svg
---

Have you saved your [CiMing2017.slack.com](https://ciming2017.slack.com) password in your LastPass vault?

<style>
  .page-content a {
    border: solid 0.1em #BCF;
    border-radius: 0.3em;
    padding: 0.1em 1em;
    background-color: #FFF;
  }
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


