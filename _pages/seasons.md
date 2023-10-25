---
title: Season Archive
permalink: /season_archive/
---

<p align="justify">
Welcome to Team 3123's FTC journey, where we share our robot designs and successes. Dive into our digital archive to explore our story, full of exciting moments and innovations. We invite you to experience our adventures in the world of robotics.
</p>

<input type="text" class= "seasonSearch" id="seasonSearch" onkeyup="myFunction()" placeholder="Search seasons..." />

<ul id="seasonList">
  {% assign sorted_seasons = site.seasons | sort: 'year' | reverse %}
{% for season in sorted_seasons %} 
  <li>
    <button type="button" class="collapsible">{{season.title}}</button>
    <div class="content">{{season.content}}</div>
  </li>
{% endfor %}

<script>
function myFunction() {
  // Declare variables
  var input, filter, ul, li, a, i, txtValue;
  input = document.getElementById('seasonSearch');
  filter = input.value.toUpperCase();
  ul = document.getElementById("seasonList");
  li = ul.getElementsByTagName('li');

  // Loop through all list items, and hide those who don't match the search query
  for (i = 0; i < li.length; i++) {
    a = li[i].getElementsByTagName("button")[0];
    txtValue = a.textContent || a.innerText;
    if (txtValue.toUpperCase().indexOf(filter) > -1) {
      li[i].style.display = "";
    } else {
      li[i].style.display = "none";
    }
  }
}

var coll = document.getElementsByClassName("collapsible");
var i;

var coll = document.getElementsByClassName("collapsible");
var i;

for (i = 0; i < coll.length; i++) {
  coll[i].addEventListener("click", function() {
    this.classList.toggle("active");
    var content = this.nextElementSibling;
    if (content.style.maxHeight){
      content.style.maxHeight = null;
    } else {
      content.style.maxHeight = content.scrollHeight + "px";
    }
  });
}

</script>
