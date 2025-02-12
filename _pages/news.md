---
title: News
permalink: /news/
#layout: wide
layout: news
author_profile: true
sidebar:
  nav: "global"
---
<h1>News Highlights</h1>

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
    display: none;
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
      <th>Article Title</th>
      <th>Publication</th>
      <th>Date</th>
    </tr>
  </thead>
  <tbody>
    {% assign sorted_links = site.data.news.links | sort: "date" | reverse %}
    {% for item in sorted_links %}
    <tr>
<!--      <td>
        <img src="{{ item.image }}" alt="{{ item.title }}">
      </td> -->
      <td>{{ item.publication }}</td>
      <td class="no-wrap">{{ item.date }}</td>
      <td><a href="{{ item.url }}" target="_blank">{{ item.title }}</a></td>
    </tr>
    {% endfor %}
  </tbody>
</table>

