---
layout: page
title: Check your Grades!
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

		const exams = {'179157': {'Midterm Exam 1': '47%'}, '101000': {'Midterm Exam 1': '22%'}, '180566': {'Midterm Exam 1': '81%'}, '179675': {'Midterm Exam 1': '57%'}, '179678': {'Midterm Exam 1': '65%'}, '180337': {'Midterm Exam 1': '47%'}, '179163': {'Midterm Exam 1': '71%'}, '178568': {'Midterm Exam 1': '61%'}, '3511': {'Midterm Exam 1': '44%'}, '178602': {'Midterm Exam 1': '73%'}, '100277': {'Midterm Exam 1': '50%'}, '181058': {'Midterm Exam 1': '58%'}, '182584': {'Midterm Exam 1': '53%'}, '178806': {'Midterm Exam 1': '25%'}, '101756': {'Midterm Exam 1': '84%'}, '183063': {'Midterm Exam 1': '69%'}, '179186': {'Midterm Exam 1': '53%'}, '100216': {'Midterm Exam 1': '66%'}, '3484': {'Midterm Exam 1': '43%'}, '103715': {'Midterm Exam 1': '51%'}, '100994': {'Midterm Exam 1': '17%'}, '4022': {'Midterm Exam 1': '25%'}, '102038': {'Midterm Exam 1': '77%'}, '178928': {'Midterm Exam 1': '52%'}, '181288': {'Midterm Exam 1': '50%'}, '178986': {'Midterm Exam 1': '68%'}, '180286': {'Midterm Exam 1': '61%'}, '178615': {'Midterm Exam 1': '72%'}, '178583': {'Midterm Exam 1': '60%'}, '178994': {'Midterm Exam 1': '8%'}, '3264': {'Midterm Exam 1': '15%'}, '4116': {'Midterm Exam 1': '38%'}, '101': {'Midterm Exam 1': '20%'}, '100292': {'Midterm Exam 1': '33%'}, '4053': {'Midterm Exam 1': '67%'}, '103969': {'Midterm Exam 1': '29%'}, '180306': {'Midterm Exam 1': '54%'}, '102967': {'Midterm Exam 1': '91%'}, '179016': {'Midterm Exam 1': '61%'}, '99904': {'Midterm Exam 1': '90%'}, '179355': {'Midterm Exam 1': '55%'}, '99787': {'Midterm Exam 1': '46%'}, '179863': {'Midterm Exam 1': '42%'}, '182065': {'Midterm Exam 1': '45%'}, '183353': {'Midterm Exam 1': '58%'}, '178299': {'Midterm Exam 1': '41%'}, '179517': {'Midterm Exam 1': '76%'}, '157331': {'Midterm Exam 1': '27%'}, '179214': {'Midterm Exam 1': '80%'}, '3483': {'Midterm Exam 1': '27%'}, '179918': {'Midterm Exam 1': '28%'}, '182845': {'Midterm Exam 1': '45%'}, '99808': {'Midterm Exam 1': '58%'}, '179784': {'Midterm Exam 1': '76%'}, '181335': {'Midterm Exam 1': '25%'}, '181190': {'Midterm Exam 1': '74%'}, '179225': {'Midterm Exam 1': '69%'}, '99825': {'Midterm Exam 1': '57%'}, '178450': {'Midterm Exam 1': '40%'}, '182207': {'Midterm Exam 1': '54%'}, '102320': {'Midterm Exam 1': '31%'}, '179232': {'Midterm Exam 1': '72%'}, '102916': {'Midterm Exam 1': '82%'}, '102920': {'Midterm Exam 1': '67%'}, '179953': {'Midterm Exam 1': '65%'}, '179592': {'Midterm Exam 1': '60%'}, '179101': {'Midterm Exam 1': '89%'}, '181479': {'Midterm Exam 1': '61%'}, '179590': {'Midterm Exam 1': '61%'}, '180703': {'Midterm Exam 1': '78%'}, '100969': {'Midterm Exam 1': '59%'}, '99776': {'Midterm Exam 1': '80%'}, '101707': {'Midterm Exam 1': '70%'}, '179240': {'Midterm Exam 1': '42%'}, '181225': {'Midterm Exam 1': '67%'}, '179958': {'Midterm Exam 1': '51%'}, '180313': {'Midterm Exam 1': '56%'}, '99760': {'Midterm Exam 1': '69%'}, '179606': {'Midterm Exam 1': '81%'}, '182933': {'Midterm Exam 1': '50%'}, '179249': {'Midterm Exam 1': '79%'}, '181996': {'Midterm Exam 1': '60%'}, '179121': {'Midterm Exam 1': '95%'}, '179383': {'Midterm Exam 1': '82%'}, '178747': {'Midterm Exam 1': '66%'}, '180570': {'Midterm Exam 1': '87%'}, '179250': {'Midterm Exam 1': '63%'}, '180537': {'Midterm Exam 1': '91%'}, '181862': {'Midterm Exam 1': '63%'}, '178912': {'Midterm Exam 1': '89%'}, '178781': {'Midterm Exam 1': '88%'}, '101335': {'Midterm Exam 1': '73%'}, '102670': {'Midterm Exam 1': '73%'}, '179996': {'Midterm Exam 1': '64%'}, '178325': {'Midterm Exam 1': '53%'}, '179178': {'Midterm Exam 1': '71%'}, '179181': {'Midterm Exam 1': '60%'}, '100992': {'Midterm Exam 1': '39%'}, '180561': {'Midterm Exam 1': '56%'}, '180538': {'Midterm Exam 1': '63%'}, '179618': {'Midterm Exam 1': '91%'}, '179146': {'Midterm Exam 1': '37%'}, '103180': {'Midterm Exam 1': '0%'}};

			projects = {'179157': {'Project 1': {'Part 1': '100%', 'Part 2': '100%', 'Part 3': '100%'}}, '101000': {'Project 1': {'Part 1': '0%', 'Part 2': '0%', 'Part 3': '0%'}}, '180566': {'Project 1': {'Part 1': '100%', 'Part 2': '100%', 'Part 3': '90%'}}, '179675': {'Project 1': {'Part 1': '100%', 'Part 2': '100%', 'Part 3': '83%'}}, '179678': {'Project 1': {'Part 1': '100%', 'Part 2': '100%', 'Part 3': '100%'}}, '180337': {'Project 1': {'Part 1': '100%', 'Part 2': '100%', 'Part 3': '86%'}}, '179163': {'Project 1': {'Part 1': '100%', 'Part 2': '100%', 'Part 3': '100%'}}, '178568': {'Project 1': {'Part 1': '100%', 'Part 2': '100%', 'Part 3': '100%'}}, '3511': {'Project 1': {'Part 1': '100%', 'Part 2': '100%', 'Part 3': '100%'}}, '178602': {'Project 1': {'Part 1': '100%', 'Part 2': '100%', 'Part 3': '72%'}}, '100277': {'Project 1': {'Part 1': '100%', 'Part 2': '100%', 'Part 3': '72%'}}, '181058': {'Project 1': {'Part 1': '100%', 'Part 2': '100%', 'Part 3': '97%'}}, '182584': {'Project 1': {'Part 1': '0%', 'Part 2': '100%', 'Part 3': '76%'}}, '178806': {'Project 1': {'Part 1': '0%', 'Part 2': '100%', 'Part 3': '0%'}}, '101756': {'Project 1': {'Part 1': '100%', 'Part 2': '100%', 'Part 3': '100%'}}, '183063': {'Project 1': {'Part 1': '100%', 'Part 2': '100%', 'Part 3': '100%'}}, '179186': {'Project 1': {'Part 1': '100%', 'Part 2': '100%', 'Part 3': '38%'}}, '100216': {'Project 1': {'Part 1': '0%', 'Part 2': '100%', 'Part 3': '83%'}}, '3484': {'Project 1': {'Part 1': '3%', 'Part 2': '0%', 'Part 3': '0%'}}, '103715': {'Project 1': {'Part 1': '100%', 'Part 2': '100%', 'Part 3': '66%'}}, '100994': {'Project 1': {'Part 1': '0%', 'Part 2': '0%', 'Part 3': '0%'}}, '4022': {'Project 1': {'Part 1': '0%', 'Part 2': '100%', 'Part 3': '45%'}}, '102038': {'Project 1': {'Part 1': '100%', 'Part 2': '100%', 'Part 3': '100%'}}, '178928': {'Project 1': {'Part 1': '100%', 'Part 2': '100%', 'Part 3': '52%'}}, '181288': {'Project 1': {'Part 1': '100%', 'Part 2': '100%', 'Part 3': '86%'}}, '178986': {'Project 1': {'Part 1': '100%', 'Part 2': '100%', 'Part 3': '100%'}}, '180286': {'Project 1': {'Part 1': '100%', 'Part 2': '100%', 'Part 3': '93%'}}, '178615': {'Project 1': {'Part 1': '100%', 'Part 2': '100%', 'Part 3': '97%'}}, '178583': {'Project 1': {'Part 1': '100%', 'Part 2': '100%', 'Part 3': '90%'}}, '178994': {'Project 1': {'Part 1': '100%', 'Part 2': '100%', 'Part 3': '93%'}}, '3264': {'Project 1': {'Part 1': '100%', 'Part 2': '100%', 'Part 3': '93%'}}, '4116': {'Project 1': {'Part 1': '100%', 'Part 2': '100%', 'Part 3': '83%'}}, '101': {'Project 1': {'Part 1': '0%', 'Part 2': '100%', 'Part 3': '66%'}}, '100292': {'Project 1': {'Part 1': '100%', 'Part 2': '100%', 'Part 3': '72%'}}, '4053': {'Project 1': {'Part 1': '100%', 'Part 2': '100%', 'Part 3': '100%'}}, '103969': {'Project 1': {'Part 1': '100%', 'Part 2': '100%', 'Part 3': '0%'}}, '180306': {'Project 1': {'Part 1': '100%', 'Part 2': '100%', 'Part 3': '86%'}}, '102967': {'Project 1': {'Part 1': '100%', 'Part 2': '100%', 'Part 3': '100%'}}, '179016': {'Project 1': {'Part 1': '100%', 'Part 2': '100%', 'Part 3': '72%'}}, '99904': {'Project 1': {'Part 1': '100%', 'Part 2': '100%', 'Part 3': '83%'}}, '179355': {'Project 1': {'Part 1': '100%', 'Part 2': '100%', 'Part 3': '100%'}}, '99787': {'Project 1': {'Part 1': '100%', 'Part 2': '100%', 'Part 3': '83%'}}, '179863': {'Project 1': {'Part 1': '100%', 'Part 2': '100%', 'Part 3': '90%'}}, '182065': {'Project 1': {'Part 1': '100%', 'Part 2': '68%', 'Part 3': '0%'}}, '183353': {'Project 1': {'Part 1': '100%', 'Part 2': '0%', 'Part 3': '100%'}}, '178299': {'Project 1': {'Part 1': '100%', 'Part 2': '100%', 'Part 3': '72%'}}, '179517': {'Project 1': {'Part 1': '100%', 'Part 2': '100%', 'Part 3': '100%'}}, '157331': {'Project 1': {'Part 1': '34%', 'Part 2': '0%', 'Part 3': '0%'}}, '179214': {'Project 1': {'Part 1': '100%', 'Part 2': '100%', 'Part 3': '100%'}}, '3483': {'Project 1': {'Part 1': '0%', 'Part 2': '100%', 'Part 3': '93%'}}, '179918': {'Project 1': {'Part 1': '100%', 'Part 2': '100%', 'Part 3': '45%'}}, '182845': {'Project 1': {'Part 1': '100%', 'Part 2': '100%', 'Part 3': '0%'}}, '99808': {'Project 1': {'Part 1': '100%', 'Part 2': '100%', 'Part 3': '93%'}}, '179784': {'Project 1': {'Part 1': '100%', 'Part 2': '100%', 'Part 3': '100%'}}, '181335': {'Project 1': {'Part 1': '100%', 'Part 2': '0%', 'Part 3': '90%'}}, '181190': {'Project 1': {'Part 1': '100%', 'Part 2': '100%', 'Part 3': '86%'}}, '179225': {'Project 1': {'Part 1': '100%', 'Part 2': '100%', 'Part 3': '72%'}}, '99825': {'Project 1': {'Part 1': '100%', 'Part 2': '100%', 'Part 3': '83%'}}, '178450': {'Project 1': {'Part 1': '100%', 'Part 2': '100%', 'Part 3': '72%'}}, '182207': {'Project 1': {'Part 1': '100%', 'Part 2': '50%', 'Part 3': '0%'}}, '102320': {'Project 1': {'Part 1': '100%', 'Part 2': '0%', 'Part 3': '0%'}}, '179232': {'Project 1': {'Part 1': '100%', 'Part 2': '100%', 'Part 3': '100%'}}, '102916': {'Project 1': {'Part 1': '100%', 'Part 2': '100%', 'Part 3': '93%'}}, '102920': {'Project 1': {'Part 1': '100%', 'Part 2': '68%', 'Part 3': '0%'}}, '179953': {'Project 1': {'Part 1': '100%', 'Part 2': '100%', 'Part 3': '90%'}}, '179592': {'Project 1': {'Part 1': '100%', 'Part 2': '100%', 'Part 3': '93%'}}, '179101': {'Project 1': {'Part 1': '100%', 'Part 2': '100%', 'Part 3': '86%'}}, '181479': {'Project 1': {'Part 1': '100%', 'Part 2': '78%', 'Part 3': '79%'}}, '179590': {'Project 1': {'Part 1': '100%', 'Part 2': '100%', 'Part 3': '83%'}}, '180703': {'Project 1': {'Part 1': '100%', 'Part 2': '100%', 'Part 3': '90%'}}, '100969': {'Project 1': {'Part 1': '100%', 'Part 2': '100%', 'Part 3': '72%'}}, '99776': {'Project 1': {'Part 1': '100%', 'Part 2': '100%', 'Part 3': '83%'}}, '101707': {'Project 1': {'Part 1': '100%', 'Part 2': '100%', 'Part 3': '100%'}}, '179240': {'Project 1': {'Part 1': '0%', 'Part 2': '100%', 'Part 3': '0%'}}, '181225': {'Project 1': {'Part 1': '100%', 'Part 2': '100%', 'Part 3': '100%'}}, '179958': {'Project 1': {'Part 1': '100%', 'Part 2': '100%', 'Part 3': '93%'}}, '180313': {'Project 1': {'Part 1': '100%', 'Part 2': '100%', 'Part 3': '100%'}}, '99760': {'Project 1': {'Part 1': '100%', 'Part 2': '100%', 'Part 3': '100%'}}, '179606': {'Project 1': {'Part 1': '100%', 'Part 2': '100%', 'Part 3': '76%'}}, '182933': {'Project 1': {'Part 1': '100%', 'Part 2': '100%', 'Part 3': '76%'}}, '179249': {'Project 1': {'Part 1': '100%', 'Part 2': '100%', 'Part 3': '62%'}}, '181996': {'Project 1': {'Part 1': '100%', 'Part 2': '100%', 'Part 3': '72%'}}, '179121': {'Project 1': {'Part 1': '100%', 'Part 2': '100%', 'Part 3': '100%'}}, '179383': {'Project 1': {'Part 1': '100%', 'Part 2': '100%', 'Part 3': '100%'}}, '178747': {'Project 1': {'Part 1': '100%', 'Part 2': '100%', 'Part 3': '69%'}}, '180570': {'Project 1': {'Part 1': '100%', 'Part 2': '100%', 'Part 3': '93%'}}, '179250': {'Project 1': {'Part 1': '100%', 'Part 2': '100%', 'Part 3': '90%'}}, '180537': {'Project 1': {'Part 1': '100%', 'Part 2': '100%', 'Part 3': '86%'}}, '181862': {'Project 1': {'Part 1': '100%', 'Part 2': '100%', 'Part 3': '79%'}}, '178912': {'Project 1': {'Part 1': '100%', 'Part 2': '100%', 'Part 3': '86%'}}, '178781': {'Project 1': {'Part 1': '100%', 'Part 2': '100%', 'Part 3': '100%'}}, '101335': {'Project 1': {'Part 1': '100%', 'Part 2': '100%', 'Part 3': '83%'}}, '102670': {'Project 1': {'Part 1': '100%', 'Part 2': '100%', 'Part 3': '0%'}}, '179996': {'Project 1': {'Part 1': '100%', 'Part 2': '100%', 'Part 3': '100%'}}, '178325': {'Project 1': {'Part 1': '100%', 'Part 2': '100%', 'Part 3': '83%'}}, '179178': {'Project 1': {'Part 1': '100%', 'Part 2': '100%', 'Part 3': '90%'}}, '179181': {'Project 1': {'Part 1': '100%', 'Part 2': '100%', 'Part 3': '93%'}}, '100992': {'Project 1': {'Part 1': '100%', 'Part 2': '100%', 'Part 3': '100%'}}, '180561': {'Project 1': {'Part 1': '100%', 'Part 2': '100%', 'Part 3': '100%'}}, '180538': {'Project 1': {'Part 1': '100%', 'Part 2': '100%', 'Part 3': '100%'}}, '179618': {'Project 1': {'Part 1': '100%', 'Part 2': '100%', 'Part 3': '100%'}}, '179146': {'Project 1': {'Part 1': '100%', 'Part 2': '100%', 'Part 3': '93%'}}, '103180': {'Project 1': {'Part 1': '0%', 'Part 2': '0%', 'Part 3': '0%'}}};

		const assignmentScores = {'Exams': exams, 'Projects': projects};

		const grades = {};
		const studentIds = Object.keys(exams);
		const assignments = Object.keys(assignmentScores);

		studentIds.forEach((id) => {
			grades[id] = {};

			assignments.forEach((assignmentType) => {
				grades[id][assignmentType] = assignmentScores[assignmentType][id];
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



















