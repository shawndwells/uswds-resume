---
permalink: /public-speaking/

layout: page
title: Public Speaking
category: CV
description: Televised interviews, radio and podcasts, and conferences.

redirect_from:
  - /speaking/
  - /conferences/
subnav:
  - text: Television
    href: '#television'
  - text: Radio & Podcasts
    href: '#radio-podcasts'
  - text: Conferences
    href: '#conferences'
---

## Television
<div class="usa-table--stacked">
  <table class="usa-table usa-table--borderless">
    <caption>Televised interviews from national and local outlets.</caption>
    <thead>
      <tr>
        <th data-sortable scope="col" role="columnheader" class="text-center">
          Date<br/>(yyyy-mm-dd)
        </th>
        <th data-sortable scope="col" role="columnheader">
          Outlet
        </th>
        <th role="columnheader">
          Title
        </th>
        <th role="columnheader">
          Description
        </th>
      </tr>
    </thead>
    <tbody>
      {% assign articles = site.data.speaking | sort:"published" | reverse %}
      {% for article in articles %}
      {% if article.type == "tv" %}
      <tr>
        <th class="text-center" data-sort-value="{{ article.published }}">
          <span style="display: inline-block; width: 7em;">{{ article.published }}</span>
        </th>
        <td class="text-left" data-sort-value="{{ article.outlet }}">
          {{ article.outlet }}
        </td>
        <td class="text-tabular text-left"><a href="{{ article.url }}">{{ article.title }}</a></td>
        <td class="text-tabular text-left">{{ article.description }}</td>
        
      </tr>
      {% endif %}
      {% endfor %} 
    </tbody>
  </table>
  <div class="usa-sr-only usa-table__announcement-region" aria-live="polite"></div>
</div>

## Radio & Podcasts
<div class="usa-table--stacked">
  <table class="usa-table usa-table--borderless">
    <caption>National radio and major podcast interviews.</caption>
    <thead>
      <tr>
        <th data-sortable scope="col" role="columnheader" class="text-center">
          Date<br/>(yyyy-mm-dd)
        </th>
        <th data-sortable scope="col" role="columnheader">
          Outlet
        </th>
        <th role="columnheader">
          Title
        </th>
        <th role="columnheader">
          Description
        </th>
      </tr>
    </thead>
    <tbody>
      {% assign articles = site.data.speaking | sort:"published" | reverse %}
      {% for article in articles %}
      {% if article.type == "radio" %}
      <tr>
        <th class="text-center" data-sort-value="{{ article.published }}">
          <span style="display: inline-block; width: 7em;">{{ article.published }}</span>
        </th>
        <td class="text-left" data-sort-value="{{ article.outlet }}">
          {{ article.outlet }}
        </td>
        <td class="text-tabular text-left"><a href="{{ article.url }}">{{ article.title }}</a></td>
        <td class="text-tabular text-left">{{ article.description }}</td>
        
      </tr>
      {% endif %}
      {% endfor %} 
    </tbody>
  </table>
  <div class="usa-sr-only usa-table__announcement-region" aria-live="polite"></div>
</div>

## Conferences
{% assign conferencePresos = site.data.presentations | sort:"sessionDate" | reverse %}

<div class="usa-table--stacked">
  <table class="usa-table usa-table--borderless">
    <caption>{{ conferencePresos.size }} conference presentations.</caption>
    <thead>
      <tr>
        <th data-sortable scope="col" role="columnheader" class="text-center">
          Date<br/>(yyyy-mm-dd)
        </th>
        <th data-sortable scope="col" role="columnheader" class="text-center">
          Event / Venue
        </th>
        <th role="columnheader" class="text-center">
          Abstract
        </th>
        <th role="columnheader" class="text-center">
          Download
        </th>
      </tr>
    </thead>
    <tbody>
      {% for presentation in conferencePresos %}
      <tr>
        <th class="text-center" data-sort-value="{{ presentation.sessionDate }}">
          <span style="display: inline-block; width: 7em;">{{ presentation.sessionDate }}</span>
        </th>
        <td class="text-left" data-sort-value="{{ presentation.eventName }}">{{ presentation.eventName }}</td>
        <td class="text-tabular text-left">
          <p class="text-tabular text-center"><a href="nowhere.com">{{ presentation.sessionName }}</a></p>
          <p class="text-tabular text-left">{{ presentation.sessionAbstract }}</p>
        </td>
        <td class="text-tabular text-center">{% if presentation.downloadPDF %}<a href="../{{ presentation.downloadPDF }}">PDF</a>{% endif %}</td>
      </tr>
      {% endfor %} 
    </tbody>
  </table>
</div>