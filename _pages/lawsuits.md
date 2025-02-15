---
title: Lawsuits
permalink: /lawsuits/
#layout: wide
layout: news
author_profile: true
sidebar:
  nav: "global"
---
<h1>Lawsuits</h1>

<p class="small">Summary of legal challenges.</p>

<a href="https://www.justsecurity.org/107087/tracker-litigation-legal-challenges-trump-administration/">Litigation Tracker: Legal Challenges to Trump Administration Actions</a>

<style>
  /* Style for a lighter separator line */
  table {
    border-collapse: collapse;
    width: 100%;
    max-width: 1200px; /* Increase width limit */
  }
  tr {
    border-bottom: 1px solid #ddd; /* Lighter line */
  }
  td {
    padding: 10px;
  }
  img {
    width: 100px;
    border-radius: 5px;
    display: block;
    margin: auto;
  }
  /* Hide headers */
  thead {
    /* display: none; */
  }
  .no-wrap {
    white-space: nowrap; /* Prevents line breaks */
  }
  .small-text-table {
    font-size: 14px; /* Adjust this size as needed */
    width: 100% !important;
    max-width: 1600px !important;
    table-layout: auto;
  }

</style>

<table class="small-text-table">
  <thead>
    <tr>
      <th>Summary</th>
      <th>Plaintiff</th>
      <th>Defendant</th>
      <th>Date Filed</th>
      <th>Lawsuit Doc</th>
      <th>Press Coverage</th>
    </tr>
  </thead>
  <tbody>
    {% assign sorted_links = site.data.lawsuits.lawsuits | sort: "date" | reverse %}
    {% for item in sorted_links %}
    <tr>
      <td>{{ item.summary }}</td>
      <td>{{ item.plaintiff }}</td>
      <td>{{ item.defendant }}</td>
      <td class="no-wrap">{{ item.date }}</td>
      <td><a href="{{ item.lawsuit-url }}" target="_blank">lawsuit pdf</a></td>
      <td><a href="{{ item.press-url }}" target="_blank">press coverage</a></td>
    </tr>
    {% endfor %}
  </tbody>
</table>

