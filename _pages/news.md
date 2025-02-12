---
title: News
permalink: /news/
#layout: wide
layout: news
author_profile: true
sidebar:
  nav: "global"
---
News highlights

<style>
/* Expand the main content area while keeping the sidebar */
.layout--archive .wrapper {
    max-width: 100% !important; /* Make full width */
    width: 95% !important; /* Adjust as needed */
    margin: auto; /* Center the content */
}

/* Expand the content area inside the wrapper */
.layout--archive .page__content {
    max-width: 1600px !important; /* Adjust width */
    width: 90% !important;
    margin: auto;
}

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

