+++
type = "static"
page = "static/single.html"
title = "About & Interviews"
description = "About Sara Soueidan — Front-end web developer, author and speaker"
menu = "main"
weight = "1"
+++


<div id="chart"></div>

<div class="goal">
	<div class="circle"></div><p>Sales 2017 RM <span id="goal"></span></p>
</div>


<div id="lastYear"></div>


<div class="goal">
	<div class="circle"></div><p>Sales 2016 RM <span id="goal2"></span></p>
</div>

<style type="text/css">
	.goal{ display: flex; align-items: center; justify-content: center; }
	.goal .circle{
		height: 10px;
		width: 10px;
		background: #28a745;
		border-radius: 50%;
		margin: 0 10px 0 0;
	}
	.goal p { margin: 0; color: #36114C; }
</style>

<script src="https://unpkg.com/frappe-charts@0.0.6/dist/frappe-charts.min.iife.js"></script>
<script type="text/javascript">

var goal = 1600;

	const data = {
    labels: ["February", "March","August", "September", "October", "November"],
    datasets: [
        {
            title: "Sales",
            values: [250,300,300, 0, 0,300]
        }
    ],
	"specific_values": [
		{
			title: "GOALS",
			line_type: "dashed",
			value: goal
		},
	]
}

const chart = new Chart({
    parent: '#chart', // or a DOM element
    title: "Income Accountability",
    data: data,
    type: 'line', // or 'line', 'scatter', 'pie', 'percentage'
    height: 250,
    colors: ['#28a745']
});

var myelement = document.getElementById("goal");
    myelement.innerHTML= 1150;

const lastYearData = {
    labels: ["January", "February","April", "May", "July", "October", "November"],
    datasets: [
        {
            title: "Sales",
            values: [300,380,450,450, 200, 200, 400]
        }
    ],
	"specific_values": [
		{
			title: "GOALS",
			line_type: "dashed",
			value: goal
		},
	]
}

const chart2 = new Chart({
    parent: '#lastYear', // or a DOM element
    title: "Last Year Income Accountability",
    data: lastYearData,
    type: 'line', // or 'line', 'scatter', 'pie', 'percentage'
    height: 250,
    colors: ['#28a745']
});



var myelement2 = document.getElementById("goal2");
    myelement2.innerHTML= 2380;


</script>