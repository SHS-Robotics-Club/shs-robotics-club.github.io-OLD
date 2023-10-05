---
title: Season Archive
permalink: /season_archive/
---

Welcome to Team 3123's FTC journey, where we share our robot designs and successes. Dive into our digital archive to explore our story, full of exciting moments and innovations. We invite you to experience our adventures in the world of robotics.

<select name="seasonSelect" id="seasonSelect" style="width: 100%;">
  <option value="" disabled selected>Select a season</option>
</select>

{% assign sorted_seasons = site.seasons | sort: 'year' | reverse %}
{% for season in sorted_seasons %}
  <script>
    var select = document.getElementById("seasonSelect");
    var option = document.createElement("option");
    option.text = "{{season.name}}";
    option.value = "{{season.year}}"
    select.add(option);
  </script>
{% endfor %}