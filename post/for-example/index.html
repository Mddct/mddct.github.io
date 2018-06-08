<div id="containerTest"  style="width: 100%;height: 500px;margin: auto;"></div>

<script type="text/javascript" src="http://echarts.baidu.com/gallery/vendors/echarts/echarts.min.js"></script>
<script type="text/javascript" src="http://echarts.baidu.com/gallery/vendors/echarts-gl/echarts-gl.min.js"></script>
<script type="text/javascript" src="http://echarts.baidu.com/gallery/vendors/echarts-stat/ecStat.min.js"></script>
<script type="text/javascript" src="http://echarts.baidu.com/gallery/vendors/echarts/extension/dataTool.min.js"></script>
<script type="text/javascript" src="http://echarts.baidu.com/gallery/vendors/echarts/map/js/china.js"></script>
<script type="text/javascript" src="http://echarts.baidu.com/gallery/vendors/echarts/map/js/world.js"></script>
<script type="text/javascript" src="http://api.map.baidu.com/api?v=2.0&ak=ZUONbpqGBsYGXNIYHicvbAbM"></script>
<script type="text/javascript" src="http://echarts.baidu.com/gallery/vendors/echarts/extension/bmap.min.js"></script>
<script type="text/javascript" src="http://echarts.baidu.com/gallery/vendors/simplex.js"></script>
<script>
    var dom = document.getElementById("containerTest");
    var myChart = echarts.init(dom);
    var app = {};
    option = null;
    var builderJson = {
    "all": 22,
    "charts": {
    "上海交通大学": 10,
    "华东理工大学": 5,
    "中航商用航空发动机有限责任公司":4,
    "中南大学": 3
    },
    "components": {
    },
    };
    var downloadJson = {
    "相同": 75,
    "不相同": 461,
    };
    var themeJson = {
    };
    var waterMarkText = '';
    var canvas = document.createElement('canvas');
    var ctx = canvas.getContext('2d');
    canvas.width = canvas.height = 100;
    ctx.textAlign = 'center';
    ctx.textBaseline = 'middle';
    ctx.globalAlpha = 0.08;
    ctx.font = '20px Microsoft Yahei';
    ctx.translate(50, 50);
    ctx.rotate(-Math.PI / 4);
    ctx.fillText(waterMarkText, 0, 0);
    option = {
    backgroundColor: {
    type: 'pattern',
    image: canvas,
    repeat: 'repeat'
    },
    tooltip: {},
    title: [{
    text: '一致的排名前四的单位',
    subtext: '总计 ' + builderJson.all,
    x: '25%',
    textAlign: 'center'
    }, {
    text: '推荐单位与所在单位是否一致的分布',
    subtext: '总计 ' + Object.keys(downloadJson).reduce(function (all, key) {
    return all + downloadJson[key];
    }, 0),
    x: '75%',
    textAlign: 'center'
    }, {
    text: '',
    subtext: '' + Object.keys(themeJson).reduce(function (all, key) {
    return all + themeJson[key];
    }, 0),
    x: '75%',
    y: '50%',
    textAlign: 'center'
    }],
    grid: [{
    top: 50,
    width: '50%',
    bottom: '45%',
    left: 10,
    containLabel: true
    }, {
    top: '55%',
    width: '50%',
    bottom: 0,
    left: 10,
    containLabel: true
    }],
    xAxis: [{
    type: 'value',
    max: builderJson.all,
    splitLine: {
    show: false
    }
    }, {
    type: 'value',
    max: builderJson.all,
    gridIndex: 1,
    splitLine: {
    show: false
    }
    }],
    yAxis: [{
    type: 'category',
    data: Object.keys(builderJson.charts),
    axisLabel: {
    interval: 0,
    rotate: 30
    },
    splitLine: {
    show: false
    }
    }, {
    gridIndex: 1,
    type: 'category',
    data: Object.keys(builderJson.components),
    axisLabel: {
    interval: 0,
    rotate: 30
    },
    splitLine: {
    show: false
    }
    }],
    series: [{
    type: 'bar',
    stack: 'chart',
    z: 3,
    label: {
    normal: {
    position: 'right',
    show: true
    }
    },
    data: Object.keys(builderJson.charts).map(function (key) {
    return builderJson.charts[key];
    })
    }, {
    type: 'bar',
    stack: 'chart',
    silent: true,
    itemStyle: {
    normal: {
    color: '#eee'
    }
    },
    data: Object.keys(builderJson.charts).map(function (key) {
    return builderJson.all - builderJson.charts[key];
    })
    }, {
    type: 'bar',
    stack: 'component',
    xAxisIndex: 1,
    yAxisIndex: 1,
    z: 3,
    label: {
    normal: {
    position: 'right',
    show: true
    }
    },
    data: Object.keys(builderJson.components).map(function (key) {
    return builderJson.components[key];
    })
    }, {
    type: 'bar',
    stack: 'component',
    silent: true,
    xAxisIndex: 1,
    yAxisIndex: 1,
    itemStyle: {
    normal: {
    color: '#eee'
    }
    },
    data: Object.keys(builderJson.components).map(function (key) {
    return builderJson.all - builderJson.components[key];
    })
    }, {
    type: 'pie',
    radius: [0, '30%'],
    center: ['75%', '25%'],
    data: Object.keys(downloadJson).map(function (key) {
    return {
    name: key.replace('.js', ''),
    value: downloadJson[key]
    }
    })
    }, {
    type: 'pie',
    radius: [0, '30%'],
    center: ['75%', '75%'],
    data: Object.keys(themeJson).map(function (key) {
    return {
    name: key.replace('.js', ''),
    value: themeJson[key]
    }
    })
    }]
    };
    if (option && typeof option === "object") {
    myChart.setOption(option, true);
    }
</script>
