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
<p id="wrong"></p>
<script>
	function displayValue() {
		const inputValue = document.getElementById("myInput").value;

		const exams = {'179157': {'Midterm Exam 1': '47%'}, '101000': {'Midterm Exam 1': '22%'}, '180566': {'Midterm Exam 1': '81%'}, '179675': {'Midterm Exam 1': '57%'}, '179678': {'Midterm Exam 1': '65%'}, '180337': {'Midterm Exam 1': '47%'}, '179163': {'Midterm Exam 1': '71%'}, '178568': {'Midterm Exam 1': '61%'}, '3511': {'Midterm Exam 1': '44%'}, '178602': {'Midterm Exam 1': '73%'}, '100277': {'Midterm Exam 1': '50%'}, '181058': {'Midterm Exam 1': '58%'}, '182584': {'Midterm Exam 1': '53%'}, '178806': {'Midterm Exam 1': '25%'}, '101756': {'Midterm Exam 1': '84%'}, '183063': {'Midterm Exam 1': '69%'}, '179186': {'Midterm Exam 1': '53%'}, '100216': {'Midterm Exam 1': '66%'}, '3484': {'Midterm Exam 1': '43%'}, '103715': {'Midterm Exam 1': '51%'}, '100994': {'Midterm Exam 1': '17%'}, '4022': {'Midterm Exam 1': '25%'}, '102038': {'Midterm Exam 1': '77%'}, '178928': {'Midterm Exam 1': '52%'}, '181288': {'Midterm Exam 1': '50%'}, '178986': {'Midterm Exam 1': '68%'}, '180286': {'Midterm Exam 1': '61%'}, '178615': {'Midterm Exam 1': '72%'}, '178583': {'Midterm Exam 1': '60%'}, '178994': {'Midterm Exam 1': '8%'}, '3264': {'Midterm Exam 1': '15%'}, '4116': {'Midterm Exam 1': '38%'}, '101': {'Midterm Exam 1': '20%'}, '100292': {'Midterm Exam 1': '33%'}, '4053': {'Midterm Exam 1': '67%'}, '103969': {'Midterm Exam 1': '29%'}, '180306': {'Midterm Exam 1': '54%'}, '102967': {'Midterm Exam 1': '91%'}, '179016': {'Midterm Exam 1': '61%'}, '99904': {'Midterm Exam 1': '90%'}, '179355': {'Midterm Exam 1': '55%'}, '99787': {'Midterm Exam 1': '46%'}, '179863': {'Midterm Exam 1': '42%'}, '182065': {'Midterm Exam 1': '45%'}, '183353': {'Midterm Exam 1': '58%'}, '178299': {'Midterm Exam 1': '41%'}, '179517': {'Midterm Exam 1': '76%'}, '157331': {'Midterm Exam 1': '27%'}, '179214': {'Midterm Exam 1': '80%'}, '3483': {'Midterm Exam 1': '27%'}, '179918': {'Midterm Exam 1': '28%'}, '182845': {'Midterm Exam 1': '45%'}, '99808': {'Midterm Exam 1': '58%'}, '179784': {'Midterm Exam 1': '76%'}, '181335': {'Midterm Exam 1': '25%'}, '181190': {'Midterm Exam 1': '74%'}, '179225': {'Midterm Exam 1': '69%'}, '99825': {'Midterm Exam 1': '57%'}, '178450': {'Midterm Exam 1': '40%'}, '182207': {'Midterm Exam 1': '54%'}, '102320': {'Midterm Exam 1': '31%'}, '179232': {'Midterm Exam 1': '72%'}, '102916': {'Midterm Exam 1': '82%'}, '102920': {'Midterm Exam 1': '67%'}, '179953': {'Midterm Exam 1': '65%'}, '179592': {'Midterm Exam 1': '60%'}, '179101': {'Midterm Exam 1': '89%'}, '181479': {'Midterm Exam 1': '61%'}, '179590': {'Midterm Exam 1': '61%'}, '180703': {'Midterm Exam 1': '78%'}, '100969': {'Midterm Exam 1': '59%'}, '99776': {'Midterm Exam 1': '80%'}, '101707': {'Midterm Exam 1': '70%'}, '179240': {'Midterm Exam 1': '42%'}, '181225': {'Midterm Exam 1': '67%'}, '179958': {'Midterm Exam 1': '51%'}, '180313': {'Midterm Exam 1': '56%'}, '99760': {'Midterm Exam 1': '69%'}, '179606': {'Midterm Exam 1': '81%'}, '182933': {'Midterm Exam 1': '50%'}, '179249': {'Midterm Exam 1': '79%'}, '181996': {'Midterm Exam 1': '60%'}, '179121': {'Midterm Exam 1': '95%'}, '179383': {'Midterm Exam 1': '82%'}, '178747': {'Midterm Exam 1': '66%'}, '180570': {'Midterm Exam 1': '87%'}, '179250': {'Midterm Exam 1': '63%'}, '180537': {'Midterm Exam 1': '91%'}, '181862': {'Midterm Exam 1': '63%'}, '178912': {'Midterm Exam 1': '89%'}, '178781': {'Midterm Exam 1': '88%'}, '101335': {'Midterm Exam 1': '73%'}, '102670': {'Midterm Exam 1': '73%'}, '179996': {'Midterm Exam 1': '64%'}, '178325': {'Midterm Exam 1': '53%'}, '179178': {'Midterm Exam 1': '71%'}, '179181': {'Midterm Exam 1': '60%'}, '100992': {'Midterm Exam 1': '39%'}, '180561': {'Midterm Exam 1': '56%'}, '180538': {'Midterm Exam 1': '63%'}, '179618': {'Midterm Exam 1': '91%'}, '179146': {'Midterm Exam 1': '37%'}, '103180': {'Midterm Exam 1': 'NONE'}};

		const grades = {};
		const student_ids = exams.keys();
		student_ids.forEach((id) => {
			[exams].forEach((assignment_type) => {
				grades[id].exams = assignment_type[id];
			});
		});

		console.log(grades[inputValue]);

		if (grades[inputValue]) {
			document.getElementById("output").textContent = JSON.stringify(grades[inputValue], null, 4);
		} else {
			alert("I don't have any grades for you!");
		}
		document.getElementById("wrong").textContent = "Email me at jxu@fisk.edu if you think there is something wrong!";
  	}
</script>



















