---
layout: page
title: endlesspint
subtitle: Simple D3 Vis of US Brewery Historical Data
tags: [code, US Breweries]
---

<style>

.bar {
  fill: steelblue;
}

.bar:hover {
  fill: brown;
}

.axis {
  font: 10px sans-serif;
}

.axis path,
.axis line {
  fill: none;
  stroke: #000;
  shape-rendering: crispEdges;
}

.x.axis path {
  display: none;
}

.line {
  fill: none;
  stroke: orange;
  stroke-width: 2.5px;
}

</style>
<body>
<script src="//d3js.org/d3.v3.min.js"></script>
<script>

var margin = {top: 20, right: 20, bottom: 30, left: 40},
    width = 864 - margin.left - margin.right,
    height = 450 - margin.top - margin.bottom;

var x = d3.scale.ordinal()
    .rangeRoundBands([0, width], .1);

var y = d3.scale.linear()
    .range([height, 0]);

var xAxis = d3.svg.axis()
    .scale(x)
    .orient("bottom");

var yAxis = d3.svg.axis()
    .scale(y)
    .orient("left")
    .ticks(10);

var line_5yr = d3.svg.line()
    .x(function(d) { return x(d.year) + x.rangeBand()/2; })
    .y(function(d) { return y(+d.total); })
    .interpolate("basis");

d3.csv("/datasets/usb/brwComp.csv", type, function(error, data) {
  if (error) throw error;

  x.domain(data.map(function(d) { return +d.year; }));
  y.domain([0, d3.max(data, function(d) { return +d.total; })]);

  console.log(data.total);
  
  var svg = d3.select("div#samesame").append("svg")
    .attr("width", width + margin.left + margin.right)
    .attr("height", height + margin.top + margin.bottom)
  .append("g")
    .attr("transform", "translate(" + margin.left + "," + margin.top + ")");

  svg.append("g")
      .attr("class", "x axis")
      .attr("transform", "translate(0," + height + ")")
      .call(xAxis)
    .selectAll("text")
      .attr("y", 0)
      .attr("x", 9)
      .attr("dy", ".35em")
      .attr("transform", "rotate(90)")
      .style("text-anchor", "start");

  svg.append("g")
      .attr("class", "y axis")
      .call(yAxis)
    .append("text")
      .attr("transform", "rotate(0)")
      .attr("x", width/2)
      .attr("y", 6)
      .attr("dy", ".71em")
      .style("text-anchor", "end")
      .text("US Brewery Count");

  svg.selectAll(".bar")
      .data(data)
    .enter().append("rect")
      .attr("class", "bar")
      .attr("x", function(d) { return x(d.year); })
      .attr("width", x.rangeBand())
      .attr("y", function(d) { return y(d.total); })
      .attr("height", function(d) { return height - y(d.total); });

  svg.append("path")
      .datum(data)
      .attr("class", "line")
      .attr("d", line_5yr);
});

function type(d) {
  d.total = +d.total;
  return d;
}

</script>
<div id="samesame"></div>

<sub>Data Source: <a href="http://www.beerinstitute.org/" target="_blank">Beer Institute</a></sub>
