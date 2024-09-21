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

<pre><code class="json" id="output"></code></pre>
<script>
	function jsonToHtml(obj) {
		if typeof obj !== 'object':
			return obj
		else:
			let html = "";
			for (let key in obj) {
				html += "<div><span class\"json-key\"><span class=\"math-inline\">\{" + key + "\:</span\> <span class\=\"json\-value\"\></span>\{" + jsonToHtml(obj[key]) + "\}</span></div>";
			}
			return html;
	}

	function displayValue() {
		const inputValue = document.getElementById("myInput").value;
		document.getElementById("output").textContent = inputValue;

		const grades = {
		    "123": {
				"HWs": {
		      		"HW0": "100%",
		    		"HW1": "50%"  			
				},
				"Labs" : {
		      		"Lab 0": "100%",
		    		"Lab 1": "50%"  
				}
			}
		};

		console.log(grades[inputValue]);
		document.getElementById("output").textContent = JSON.stringify(grades[inputValue]); 
		document.getElementById("output").innerHTML = jsonToHtml(grades[inputValue]); 
  	}
</script>