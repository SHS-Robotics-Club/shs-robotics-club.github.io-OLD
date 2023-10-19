---
title: Season Archive
permalink: /season_archive_old/
---

Welcome to Team 3123's FTC journey, where we share our robot designs and successes. Dive into our digital archive to explore our story, full of exciting moments and innovations. We invite you to experience our adventures in the world of robotics.

<select id="seasonSelect" style="width: 100%;">
  <option value="select" disabled selected>Select a season</option>
</select>

<p id="demo"></p>

{% assign sorted_seasons = site.seasons | sort: 'year' | reverse %}
<script>
  var select = document.getElementById("seasonSelect");
  var input = document.querySelector('input[type="button"]');
  var seasons = [
    {% for season in sorted_seasons %}{"title": "{{season.title}}", "year": "{{season.year}}" }, 
    {% endfor %}{}
  ];

  for(var i = 0, size = seasons.length; i < size-1 ; i++){
    var item = seasons[i];
    var option = document.createElement("option");
    option.text = item.title;
    option.value = item.year;
    select.add(option);
  }

  var p = document.getElementById("demo");
  select.addEventListener('change',function(){
    p.textContent = select.value;
  });
</script>

<div class="season-content">
  {% for season in sorted_seasons %}
  <div class="{{season.year}} hide">
    {{season.content}}
  </div>
  {% endfor %}
</div>