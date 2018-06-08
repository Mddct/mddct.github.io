<!--more-->
# 分析步骤
```sequence
Title: 第十批千人计划test
test->test1: test
test1-->test2: test
test2->>test3: test
test3-->>test: test
```

# testing0
{{< partial "for-example.html" >}}

# testing0.0
{{< partial "distributes2.html" >}}

# testing0.1
{{< partial "11.html" >}}

# testing0.2
{{< partial "12.html" >}}

# testing0.3
{{< partial "2.html" >}}

# testing0.4
{{< partial "3.html" >}}

# testing0.5
{{< partial "4.html" >}}

# testing0.6
{{< partial "5.html" >}}

# testing0.7
{{< partial "6.html" >}}

# testing0.8
{{< partial "7.html" >}}

# testing1
{{< partial "distributed.html" >}}

<!-- # 分析结果 -->

<!-- ## echart Test  -->
<!-- ## 专业领域 -->
<!-- ![专业领域](/2pic.jpg "img") -->
<!-- ## 籍贯分布1 -->
<!-- ![籍贯分布](/3pic.jpg "img") -->

<!-- ## 籍贯分布2 -->
<!-- ![籍贯分布2](/6pic.jpg "img") -->
<!-- ## 男女数量 -->
<!-- ![男女数量](/4pic.jpg "img") -->

<!-- ## 推荐单位 -->
<!-- ![推荐单位](/5pic.jpg "img") -->

<!-- ## More [TODO] -->

<!-- # js代码 -->
<!-- ```js -->
<!-- option1 = { -->
<!-- backgroundColor: '#6c343c', -->

<!-- title: { -->
<!-- text: '籍贯分布不完全统计', -->
<!-- left: 'center', -->
<!-- top: 20, -->
<!-- textStyle: { -->
<!-- color: '#ccc' -->
<!-- } -->
<!-- }, -->

<!-- tooltip : { -->
<!-- trigger: 'item', -->
<!-- formatter: "{a} <br/>{b} : {c} ({d}%)" -->
<!-- }, -->

<!-- visualMap: { -->
<!-- show: false, -->
<!-- min: 80, -->
<!-- max: 600, -->
<!-- inRange: { -->
<!-- colorLightness: [0, 1] -->
<!-- } -->
<!-- }, -->
<!-- series : [ -->
<!-- { -->
<!-- name:'访问来源', -->
<!-- type:'pie', -->
<!-- radius : '55%', -->
<!-- center: ['50%', '50%'], -->
<!-- data:[ -->
<!-- {value:7, name:'安徽'}, -->
<!-- {value:12, name:'江苏'}, -->
<!-- {value:12, name:'浙江'}, -->
<!-- {value:8, name:'湖北'}, -->
<!-- {value:7, name:'湖南'}, -->
<!-- {value:5, name:'山东'}, -->
<!-- {value:5, name:'四川'}, -->
<!-- {value:5, name:'辽宁'}, -->
<!-- {value:4, name:'河南'}, -->
<!-- {value:4, name:'上海'}, -->
<!-- {value:6, name:'美籍'}, -->
<!-- {value:4, name:'福建'}, -->
<!-- {value:3, name:'河北'}, -->
<!-- {value:2, name:'重庆'}, -->
<!-- {value:2, name:'江西'} -->
<!-- ].sort(function (a, b) { return a.value - b.value; }), -->
<!-- roseType: 'radius', -->
<!-- label: { -->
<!-- normal: { -->
<!-- textStyle: { -->
<!-- color: 'rgba(255, 255, 255, 0.3)' -->
<!-- } -->
<!-- } -->
<!-- }, -->
<!-- labelLine: { -->
<!-- normal: { -->
<!-- lineStyle: { -->
<!-- color: 'rgba(255, 255, 255, 0.3)' -->
<!-- }, -->
<!-- smooth: 0.2, -->
<!-- length: 10, -->
<!-- length2: 20 -->
<!-- } -->
<!-- }, -->
<!-- itemStyle: { -->
<!-- normal: { -->
<!-- color: '#000000', -->
<!-- shadowBlur: 200, -->
<!-- shadowColor: 'rgba(0, 0, 0, 0.5)' -->
<!-- } -->
<!-- }, -->

<!-- animationType: 'scale', -->
<!-- animationEasing: 'elasticOut', -->
<!-- animationDelay: function (idx) { -->
<!-- return Math.random() * 200; -->
<!-- } -->
<!-- } -->
<!-- ] -->
<!-- }; -->






<!-- option2 = { -->
<!-- title: { -->
<!-- text: '推荐单位统计', -->
<!-- subtext: '数据' -->
<!-- }, -->
<!-- tooltip: { -->
<!-- trigger: 'axis', -->
<!-- axisPointer: { -->
<!-- type: 'shadow' -->
<!-- } -->
<!-- }, -->
<!-- legend: { -->

<!-- }, -->
<!-- grid: { -->
<!-- left: '3%', -->
<!-- right: '4%', -->
<!-- bottom: '3%', -->
<!-- containLabel: true -->
<!-- }, -->
<!-- xAxis: { -->
<!-- type: 'value', -->
<!-- boundaryGap: [0, 0.01] -->
<!-- }, -->
<!-- yAxis: { -->
<!-- type: 'category', -->
<!-- data: ['复旦大学','上海交通大学','北京大学', -->
<!-- '中国科学技术大学','清华大学','南京大学','中南大学','浙江大学' -->
<!-- ,'哈尔滨工业大学','同济大学','中国科学院上海生命科学研究院','中航商用航空发动机有限责任公司','西安交通大学', -->
<!-- '上海交通大学','华东理工大学','中山大学','华中科技大学','四川大学','大连理工大学'] -->
<!-- }, -->
<!-- series: [ -->

<!-- { -->
<!-- name: '推荐单位统计', -->
<!-- type: 'bar', -->
<!-- data: [138, 33, 28, 31, 17, 10,8,13,8,11,8,6,6,6,5,5,6,5,5] -->
<!-- } -->
<!-- ] -->
<!-- }; -->






<!-- var  option = { -->
<!-- title : { -->
<!-- text: '姓氏统计', -->
<!-- subtext: '选取了数量较多的几种姓氏', -->
<!-- x:'center' -->
<!-- }, -->
<!-- tooltip : { -->
<!-- trigger: 'item', -->
<!-- formatter: "{a} <br/>{b} : {c} ({d}%)" -->
<!-- }, -->
<!-- legend: { -->
<!-- orient: 'vertical', -->
<!-- left: 'left', -->
<!-- data: ['王','李','张','陈','刘','徐','黄','周','赵','杨','孙','朱','吴','肖','马','陆',] -->
<!-- }, -->
<!-- series : [ -->
<!-- { -->
<!-- name: '访问来源', -->
<!-- type: 'pie', -->
<!-- radius : '55%', -->
<!-- center: ['50%', '60%'], -->
<!-- data:[ -->
<!-- {value:43, name:'王'}, -->
<!-- {value:34, name:'李'}, -->
<!-- {value:29, name:'张'}, -->
<!-- {value:28, name:'陈'}, -->
<!-- {value:28, name:'刘'}, -->
<!-- {value:16, name:'徐'}, -->
<!-- {value:16, name:'黄'}, -->
<!-- {value:15, name:'周'}, -->
<!-- {value:13, name:'赵'}, -->
<!-- {value:12, name:'杨'}, -->
<!-- {value:11, name:'孙'}, -->
<!-- {value:10, name:'朱'}, -->
<!-- {value:9, name:'吴'}, -->
<!-- {value:8, name:'肖'}, -->
<!-- {value:7, name:'马'}, -->
<!-- {value:6, name:'陆'}, -->
<!-- ], -->
<!-- itemStyle: { -->
<!-- emphasis: { -->
<!-- shadowBlur: 10, -->
<!-- shadowOffsetX: 0, -->
<!-- shadowColor: 'rgba(0, 0, 0, 0.5)' -->
<!-- } -->
<!-- } -->
<!-- } -->
<!-- ] -->
<!-- }; -->
<!-- ``` -->
