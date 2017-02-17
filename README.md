# StopTheClock
Code Ramp Project

<!DOCTYPE html>
<!-- saved from url=(0041)file:///D:/Code%20Ramp/timemangement.html -->
<html>
	<head><meta http-equiv="Content-Type" content="text/html; charset=windows-1252">	
	<style>
	.activity{
		padding-left: 10px
	}
	</style>
	</head>

	<body>
		  <script src="https://code.jquery.com/jquery-2.1.1.js"></script>

		<h1>Stop the Clock </h1>
		<div class="container">
  	
  		<h2>Time Tracker</h2>
  		<form id="timeform" action="" name="time tracker">

  		</form>


  		<script>
  		for (i = 1; i < 25; i++) { 
  			$("#timeform").append("<label for='Duration'>hour " + i + "</label>" );
  			$('#timeform').append("<input class='activity' text='text'  placeholder='Activity'/><br>")
        

    	}	
$('#timeform').append('<button type="submit">submit</button>')
  		</script>
  		<script src="http://d3js.org/d3.v3.min.js"></script>
<script>

var width = 960,
    height = 500,
    radius = Math.min(width, height) / 2;

var color = d3.scale.ordinal()
    .range(["#98abc5", "#8a89a6", "#7b6888", "#6b486b", "#a05d56", "#d0743c", "#ff8c00"]);

var arc = d3.svg.arc()
    .outerRadius(radius - 10)
    .innerRadius(0);

var labelArc = d3.svg.arc()
    .outerRadius(radius - 40)
    .innerRadius(radius - 40);

var pie = d3.layout.pie()
    .sort(null)
    .value(function(d) { return d.hours; });

var svg = d3.select("body").append("svg")
    .attr("width", width)
    .attr("height", height)
  .append("g")
    .attr("transform", "translate(" + width / 2 + "," + height / 2 + ")");

var data= [
			{"activity": "email", "hours":3},
			{"activity": "social media", "hours":3},
			{"activity": "idle", "hours":3},
			{"activity": "personal care", "hours":3},
			{"activity": "eating", "hours":3},
			{"activity": "sleeping", "hours":3}]
  var g = svg.selectAll(".arc")
      .data(pie(data))
    .enter().append("g")
      .attr("class", "arc");

  g.append("path")
      .attr("d", arc)
      .style("fill", function(d) { return color(d.data.activity); });

  g.append("text")
      .attr("transform", function(d) { return "translate(" + labelArc.centroid(d) + ")"; })
      .attr("dy", ".35em")
      .text(function(d) { return d.data.activity; });
</script>

	</body>
</html>
