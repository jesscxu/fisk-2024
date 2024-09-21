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

    const grades = {
    	'123': {
    		'HWs': {
	      		'HW0': '100%',
	    		'HW1': '50%',  			
    		},
    		'Labs' : {
	      		'Lab 0': '100%',
	    		'Lab 1': '50%',  
    		}
    	}
    };

    console.log(grades[inputValue]);
    // document.getElementById("output").textContent = grades[inputValue]; 
  }
</script>

<p id="output"></p>