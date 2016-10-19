---
title: Points
nav-icon: /assets/four-dots.svg
---



<style>
  .student-tasks-grid span {
  display: inline-block;
  border-radius: 1em;
  padding: 0.3em;
  }
  .student-tasks-grid span.done .number {
  background-color: #EEE;
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
    {% assign compSize = student[1].completed | size %}
    {% assign inproSize = student[1].inProgress | size %}
    {% assign listSize = compSize + inproSize %}
    <span class="
    {% if listSize > 1 %}
    done
    {% else %}
    yet-to-do
    {% endif %}
    ">
      <span class="number">
        {{ student[0] }}
      </span>
      <span>
        {{ student[1].completed | join: " // " }}
      </span>
      <span class="{% if inproSize > 0 %}yet-to-do{% endif %}">
        {{ student[1].inProgress | join: " // " }}
      </span>
    </span>
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
      {% assign biro = student[1].biro | size %}
      {% assign budgies = student[1].budgies | size %}
      {% assign superblocks = student[1].superblocks | size %}
      {% assign spectacles = student[1].spectacles | size %}
      {% assign moon = student[1].road-moon | size %}
      {% assign lettuce = student[1].regrow-lettuce | size %}
      {% assign roommates = student[1].unusual-roommates | size %}
      {% assign introductions = student[1].self-introductions | size %}
      {% assign total = biro | plus: budgies | plus: superblocks | plus: spectacles | plus: moon | plus: lettuce | plus: roommates | plus: introduction %}
      {{ total }}
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

