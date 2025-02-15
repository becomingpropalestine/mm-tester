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

<p class="small">Curated news highlights to help wake you up.</p>

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

  .small-text-table {
    font-size: 14px; /* Adjust this size as needed */
    width: 100% !important;
    max-width: 1600px !important;
    table-layout: auto;
  }


@media (min-width: 1200px) {
  td.no-wrap {
    white-space: nowrap; /* Prevents line breaks */
  }
}


@media (max-width: 768px) {
  .hide-on-mobile {
    display: none;
  }
}



/* General style for highlighted text inside <p> */
.highlight-test {
  padding: 3px 6px; /* Small padding to separate text from background */
  font-size: 12px; /* Adjust text size */
  font-weight: normal;
  border-radius: 3px; /* Rounded corners */
  color: white; /* White text for contrast */
  text-align: center;
}


.highlight-text {
  padding: 1px 2px; /* Small padding to separate text from background */
  font-size: 12px; /* Adjust text size */
  font-weight: bold;
  border-radius: 3px; /* Rounded corners */
  color: white; /* White text for contrast */
}

/* Specific colors for each type */
.type-election-interference {
  background-color: #007bff; /* Blue */
}

.type-general {
  background-color: #dc3545; /* Red */
}

.type-ideology {
  background-color: #28a745; /* Green */
}

.type-federal-workforce {
  background-color: #fd7e14; /* Orange */
}

.type-technology {
  background-color: #6f42c1; /* Purple */
}

.type-unknown {
  background-color: #6c757d; /* Gray */
}






</style>


<!-- ORIGINAL TABLE

Topic: All

<table class="small-text-table">
  <thead>
    <tr>
      <th>Article Title</th>
      <th>Publication</th>
      <th>Date</th>
      <th>Type</th>
    </tr>
  </thead>
  <tbody>
    {% assign news_links = site.data.news.links | sort: "date" | reverse %}
    {% for item in news_links %}
    <tr>
      <td>{{ item.publication }}</td>
      <td class="no-wrap">{{ item.date }}</td>
      <td>{{ item.type }}</td>
      <td><a href="{{ item.url }}" target="_blank">{{ item.title }}</a> (<a href="{{ item.no-paywall }}" target="_blank">no paywall</a>)</td>
    </tr>
    {% endfor %}
  </tbody>
</table>

-->



<button onclick="resetTable()">Show All</button>
<button class="type-election-interference" onclick="filterTable('election interference')">Show Election Interference Articles</button>
<button class="type-federal-workforce" onclick="filterTable('federal workforce')">Show Federal Workforce Articles</button>
<button class="type-ideology" onclick="filterTable('ideology')">Show Ideology Articles</button>
<button class="type-general" onclick="filterTable('general')">Show General Articles</button>


<table class="small-text-table">
  <thead>
    <tr>
      <th>Article Title</th>
      <th>Publication</th>
      <th>Type</th>
      <th>Date</th>
    </tr>
  </thead>
  <tbody>
    {% assign sorted_links = site.data.news.links | sort: "date" | reverse %}
    {% for item in sorted_links %}
    <tr data-type="{{ item.type }}">
      <td>{{ item.publication }}</td>
      <td class="no-wrap">{{ item.date }}</td>
      <td class="no-wrap hide-on-mobile"><div class="highlight-test type-{{ item.type | downcase | replace: ' ', '-' }}">{{ item.type }}</div></td>
      <td><a href="{{ item.url }}" target="_blank">{{ item.title }}</a> (<a href="{{ item.no-paywall }}" target="_blank">no paywall</a>)</td>
    </tr>
    {% endfor %}
  </tbody>
</table>

<script>
  function filterTable(filterType) {
    let rows = document.querySelectorAll("table tbody tr");

    rows.forEach(row => {
      if (row.dataset.type === filterType) {
        row.style.display = "";  // Show matching rows
      } else {
        row.style.display = "none";  // Hide non-matching rows
      }
    });
  }

  function resetTable() {
    let rows = document.querySelectorAll("table tbody tr");
    rows.forEach(row => row.style.display = "");  // Show all rows
  }
</script>

