---
layout: post
title: "曲线图"
description: "curve chart"
category: js
date: 2017-12-19 10:49:51 +0800
tag: [js]
---

# 图例
<div id="container" style="min-width: 310px; height: 410px; margin: 0 auto"></div>
<script src="http://www.17sucai.com//preview/67625/2017-11-23/zhutu1/js/jquery.min.js"></script>
<script src="http://cdn.hcharts.cn/highcharts/highcharts.js"></script>
<script type="text/javascript">
	var daysOfMonth = [];
	var fullYear = new Date().getFullYear();
	var month = new Date().getMonth() + 1;
	for (var i = 1; i <= 7; i++) {
	  daysOfMonth.push(month + '-' + i);
	}
	var options = {
    chart: {
      type: 'spline'//指定图表的类型，默认是折线图（line）
    },
    title: {
      text: fullYear+'/'+month+'收益报表'// 标题
    },
    xAxis: {
      categories: daysOfMonth// x 轴分类
    },
    yAxis: {
      title: {
          text: '月'// y 轴标题
      }
    },
    series: [{ // 数据列
      name: '12月', // 数据列名
      data: [1000, 0, 5000, 10000, 15000, 16000, 21000, 30000, 30000, 1000, 0, 5000, 10000, 15000, 16000, 21000, 0, 20000,1000, 0, 5000, 10000, 15000, 16000, 21000, 30000, 20000, 16000, 21000, 30000, 20000]// 数据
    },{
      name: '11月',
      data: [3000, 0, 5000, 10000, 15000, 16000, 23000, 50000, 30000, 1000, 100, 5000, 10000, 15000, 16000, 21000, 0, 20000,1000, 0, 5000, 10000, 15000, 16000, 21000, 30000, 20000, 16000, 21000, 30000, 50000]
    }]
	};
	// 图表初始化函数
	Highcharts.chart('container', options);
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
	var daysOfMonth = [];
	var fullYear = new Date().getFullYear();
	var month = new Date().getMonth() + 1;
	for (var i = 1; i <= 7; i++) {
	  daysOfMonth.push(month + '-' + i);
	}
	var options = {
    chart: {
      type: 'spline'//指定图表的类型，默认是折线图（line）
    },
    title: {
      text: fullYear+'/'+month+'收益报表'// 标题
    },
    xAxis: {
      categories: daysOfMonth// x 轴分类
    },
    yAxis: {
      title: {
          text: '月'// y 轴标题
      }
    },
    series: [{ // 数据列
      name: '12月', // 数据列名
      data: [1000, 0, 5000, 10000, 15000, 16000, 21000, 30000, 30000, 1000, 0, 5000, 10000, 15000, 16000, 21000, 0, 20000,1000, 0, 5000, 10000, 15000, 16000, 21000, 30000, 20000, 16000, 21000, 30000, 20000]// 数据
    },{
      name: '11月',
      data: [3000, 0, 5000, 10000, 15000, 16000, 23000, 50000, 30000, 1000, 100, 5000, 10000, 15000, 16000, 21000, 0, 20000,1000, 0, 5000, 10000, 15000, 16000, 21000, 30000, 20000, 16000, 21000, 30000, 50000]
    }]
	};
	// 图表初始化函数
	Highcharts.chart('container', options);
</script>
````
		




