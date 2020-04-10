---
layout: post
title: "柱状图"
description: "column chart"
categorys: js
date: 2017-12-19 13:39:51 +0800
tag: [js]
---

# 图例
<div id="container" style="min-width: 310px; height: 410px; margin: 0 auto"></div>
<script src="http://www.17sucai.com//preview/67625/2017-11-23/zhutu1/js/jquery.min.js"></script>
<script src="http://cdn.hcharts.cn/highcharts/highcharts.js"></script>
<script type="text/javascript">
	$(document).ready(function() {
	  var chart = { type: 'column' };
	  var title = { text: '最近30天各级预警CASE分布图' };
	  var xAxis = {
	    categories: [
	      '2017/10/01', '2017/10/02', '2017/10/03', '2017/10/04', '2017/10/05', '2017/10/06', '2017/10/07', '2017/10/08', '2017/10/09', '2017/10/10', '2017/10/11', '2017/10/12', '2017/10/13', '2017/10/14', '2017/10/15', '2017/10/16', '2017/10/17', '2017/10/18', '2017/10/19', '2017/10/20', '2017/10/21', '2017/10/22', '2017/10/23', '2017/10/24', '2017/10/25', '2017/10/26', '2017/10/27', '2017/10/28', '2017/10/29', '2017/10/30'
	    ],
	    maxZoom:30,
	    labels: {
	      x:0,//调节x偏移
	      rotation: 45, //旋转,效果就是影响标签的显示方向
	    },
	    opposite : false,// 天显示X轴上与下
	    type: 'datetime',
	    title : {
	      align : 'high',
	      text : '天',
	      style : {
	          color : '#000',
	          fontSize : '11px'
	      }
	    },
	  };

	  var credits = { enabled : false };
	  var yAxis = {
	    min: 0,
	    tickPositions: [0, 10, 20, 30,40,50] ,// 指定竖轴坐标点的值
	    title: {
	        text: 'CASE数'
	    },
	    stackLabels: {
	      enabled: true,
	      style: {
	        fontWeight: 'bold',
	        color: (Highcharts.theme && Highcharts.theme.textColor) || 'gray'
	      }
	    }
	  };
	  var tooltip = {
	    shared:true,
	    crosshairs:true,
	    dateTimeLabelFormats:{
	      day:"%Y-%m-%d",
	    },
	  };
	  var plotOptions = {
	    series: { pointPadding:0.2 },
	    column: {
	      //percent置顶
	      stacking: 'normal',
	      pointPadding: 0.2,
	      pointWidth: 15 , //柱子的宽度30px
	      // 如果x轴一个点有两个柱，则这个属性设置的是这两个柱的间距。
	      groupPadding : 0.5,
	    }
	  };
	  var legend = {
	    align: 'center',
	    x: -30,
	    verticalAlign: 'bottom',
	    y: 15,
	    floating: true,
	    backgroundColor: (Highcharts.theme && Highcharts.theme.background2) || 'white',
	    shadow: false
	  };
	  var series= [{
	    name: '三级预警',
	    color:'#fe0100',
	    data: [5, 3, 4, 7, 2,10,1,1,1,1,1,5,5, 3, 4, 7, 2,10,1,1,1,1,1,5,1,2,3,4,5,6]
	  }, {
	    name: '二级预警',
	    color:'#ff9803',
	    data: [2, 2, 3, 2, 1,10,1,1,1,1,1,5,5, 3, 4, 7, 2,10,1,1,1,1,1,5,1,2,3,4,5,6]
	  }, {
	    name: '一级预警',
	    color:'#fffe00',
	    data: [3, 4, 4, 2, 5,10,1,1,1,1,1,5,5, 3, 4, 7, 2,10,1,1,1,1,1,5,1,2,3,4,5,6]
	  }, {
	    name: '正常',
	    color:'#01cd00',
	    data: [3, 4, 4, 2, 5,10,1,1,1,1,1,5,5, 3, 4, 7, 2,10,1,1,1,1,1,5,1,2,3,4,5,6]
	  }]
	  var json = {};
	  json.chart = chart;
	  json.title = title;
	  json.xAxis = xAxis;
	  json.yAxis = yAxis;
	  json.legend = legend;
	  json.tooltip = tooltip;
	  json.plotOptions = plotOptions;
	  json.credits = credits;
	  json.series = series;
	  $('#container').highcharts(json);
	});
</script>
# html代码
```
<div id="container" style="min-width: 310px; height: 400px; margin: 0 auto"></div>
````

# js代码
```
<script src="http://www.17sucai.com//preview/67625/2017-11-23/zhutu1/js/jquery.min.js"></script>
<script src="http://cdn.hcharts.cn/highcharts/highcharts.js"></script>
<script type="text/javascript">
	$(document).ready(function() {
	  var chart = { type: 'column' };
	  var title = { text: '最近30天各级预警CASE分布图' };
	  var xAxis = {
	    categories: [
	      '2017/10/01', '2017/10/02', '2017/10/03', '2017/10/04', '2017/10/05', '2017/10/06', '2017/10/07', '2017/10/08', '2017/10/09', '2017/10/10', '2017/10/11', '2017/10/12', '2017/10/13', '2017/10/14', '2017/10/15', '2017/10/16', '2017/10/17', '2017/10/18', '2017/10/19', '2017/10/20', '2017/10/21', '2017/10/22', '2017/10/23', '2017/10/24', '2017/10/25', '2017/10/26', '2017/10/27', '2017/10/28', '2017/10/29', '2017/10/30'
	    ],
	    maxZoom:30,
	    labels: {
	      x:0,//调节x偏移
	      rotation: 45, //旋转,效果就是影响标签的显示方向
	    },
	    opposite : false,// 天显示X轴上与下
	    type: 'datetime',
	    title : {
	      align : 'high',
	      text : '天',
	      style : {
	          color : '#000',
	          fontSize : '11px'
	      }
	    },
	  };

	  var credits = { enabled : false };
	  var yAxis = {
	    min: 0,
	    tickPositions: [0, 10, 20, 30,40,50] ,// 指定竖轴坐标点的值
	    title: {
	        text: 'CASE数'
	    },
	    stackLabels: {
	      enabled: true,
	      style: {
	        fontWeight: 'bold',
	        color: (Highcharts.theme && Highcharts.theme.textColor) || 'gray'
	      }
	    }
	  };
	  var tooltip = {
	    shared:true,
	    crosshairs:true,
	    dateTimeLabelFormats:{
	      day:"%Y-%m-%d",
	    },
	  };
	  var plotOptions = {
	    series: { pointPadding:0.2 },
	    column: {
	      //percent置顶
	      stacking: 'normal',
	      pointPadding: 0.2,
	      pointWidth: 15 , //柱子的宽度30px
	      // 如果x轴一个点有两个柱，则这个属性设置的是这两个柱的间距。
	      groupPadding : 0.5,
	    }
	  };
	  var legend = {
	    align: 'center',
	    x: -30,
	    verticalAlign: 'bottom',
	    y: 15,
	    floating: true,
	    backgroundColor: (Highcharts.theme && Highcharts.theme.background2) || 'white',
	    shadow: false
	  };
	  var series= [{
	    name: '三级预警',
	    color:'#fe0100',
	    data: [5, 3, 4, 7, 2,10,1,1,1,1,1,5,5, 3, 4, 7, 2,10,1,1,1,1,1,5,1,2,3,4,5,6]
	  }, {
	    name: '二级预警',
	    color:'#ff9803',
	    data: [2, 2, 3, 2, 1,10,1,1,1,1,1,5,5, 3, 4, 7, 2,10,1,1,1,1,1,5,1,2,3,4,5,6]
	  }, {
	    name: '一级预警',
	    color:'#fffe00',
	    data: [3, 4, 4, 2, 5,10,1,1,1,1,1,5,5, 3, 4, 7, 2,10,1,1,1,1,1,5,1,2,3,4,5,6]
	  }, {
	    name: '正常',
	    color:'#01cd00',
	    data: [3, 4, 4, 2, 5,10,1,1,1,1,1,5,5, 3, 4, 7, 2,10,1,1,1,1,1,5,1,2,3,4,5,6]
	  }]
	  var json = {};
	  json.chart = chart;
	  json.title = title;
	  json.xAxis = xAxis;
	  json.yAxis = yAxis;
	  json.legend = legend;
	  json.tooltip = tooltip;
	  json.plotOptions = plotOptions;
	  json.credits = credits;
	  json.series = series;
	  $('#container').highcharts(json);
	});
</script>
````
		




