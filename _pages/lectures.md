---
layout: schedule
permalink: /schedule/
title: Schedule
description: Sixteen-week master plan. Required-reading changes receive at least ten days' notice.
---

{% for lecture in site.data.lectures %}
<tr>
    <th scope="row">{{ lecture.date }}</th>
    {% if lecture.title contains 'No class' or lecture.title contains 'No classes' or lecture.title contains 'cancelled' or lecture.title contains 'Buffer' or lecture.title contains 'Midterm' %}
        <td colspan="3" class="schedule-special-session">
            <div class="schedule-special-title">{{ lecture.title }}</div>
            {% include schedule-logistics.html items=lecture.logistics %}
        </td>
    {% else %}
    <td>
        {% if lecture.title %}
            <ul class="schedule-session-list">
            {% for title in lecture.title %}
                <li>{{ title }}</li>
            {% endfor %}
            </ul>
        {% endif %}

        {% if lecture.guest %}
            {% for guest in lecture.guest %}
                <div class="guest-lecturer">
                    Guest lecturer:<br />
                    <a href="{{ guest.profile }}" target="_blank">{{ guest.name }}</a>, {{ guest.affil }}
                </div>
                {% if guest.photo %}
                    <a href="{{ guest.profile }}" target="_blank">
                        <img class="guest-photo" src="{{ guest.photo }}" alt="Photo of {{ guest.name }}" />
                    </a>
                {% endif %}
            {% endfor %}
        {% endif %}
    </td>
    <td>
        {% if lecture.readings %}
        Main readings:
        <ul class="space_list">
        {% for reading in lecture.readings %}
            <li>{{ reading }}</li>
        {% endfor %}
        </ul>
        {% endif %}
        {% if lecture.optional %}
        Optional readings:
        <ul class="space_list_no_indent">
            {% for optional in lecture.optional %}
                <li>{{ optional }}</li>
            {% endfor %}
        </ul>
        {% endif %}
    </td>
    <td class="schedule-logistics-cell">
        {% include schedule-logistics.html items=lecture.logistics %}
    </td>
    {% endif %}
</tr>
{% endfor %}
