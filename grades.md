---
layout: page
title: Check my Grade!
description: How you can check your current grades in the class!
---

## Grades

<br>
<p>Type in your student ID:</p>
<input type="text" id="myInput">
<button onclick="displayValue()">Get my GRADES!</button>

<script>
  function displayValue() {
    let inputValue = document.getElementById("myInput").value;
    document.getElementById("output").textContent = inputValue; 
  }
</script>

<p id="output"></p>