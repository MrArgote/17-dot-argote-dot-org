---
title: Points
nav-icon: /points.svg
---



<style>
  .student-tasks-grid span {
  display: inline-block;
  border-radius: 1em;
  padding: 0.3em;
  }
  .student-tasks-grid span.yet-to-do .number {
  background-color: #EEE;
}
  .student-tasks-grid span.done {
  background-color: #2F8;
  }
  .student-tasks-grid span.yet-to-do {
  background-color: #F4A;
  }
</style>

Dropbox:

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

