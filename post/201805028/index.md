<script type="text/javascript" src="http://echarts.baidu.com/gallery/vendors/echarts/echarts.min.js"></script>
       <script type="text/javascript" src="http://echarts.baidu.com/gallery/vendors/echarts-gl/echarts-gl.min.js"></script>
       <script type="text/javascript" src="http://echarts.baidu.com/gallery/vendors/echarts-stat/ecStat.min.js"></script>
       <script type="text/javascript" src="http://echarts.baidu.com/gallery/vendors/echarts/extension/dataTool.min.js"></script>
       <script type="text/javascript" src="http://echarts.baidu.com/gallery/vendors/echarts/map/js/china.js"></script>
       <script type="text/javascript" src="http://echarts.baidu.com/gallery/vendors/echarts/map/js/world.js"></script>
       <script type="text/javascript" src="http://api.map.baidu.com/api?v=2.0&ak=ZUONbpqGBsYGXNIYHicvbAbM"></script>
       <script type="text/javascript" src="http://echarts.baidu.com/gallery/vendors/echarts/extension/bmap.min.js"></script>
       <script type="text/javascript" src="http://echarts.baidu.com/gallery/vendors/simplex.js"></script>
       <div id="containerTest"  style="width: 100%;height: 500px;margin: auto;"></div>
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


<!--more-->


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



# 分析步骤
```sequence
Title: 第十批千人计划test
test->test1: test
test1-->test2: test
test2->>test3: test
test3-->>test: test
```
# 分析结果

## echart Test 
## 专业领域
![专业领域](/2pic.jpg "img")
## 籍贯分布1
![籍贯分布](/3pic.jpg "img")

## 籍贯分布2
![籍贯分布2](/6pic.jpg "img")
## 男女数量
![男女数量](/4pic.jpg "img")

## 推荐单位
![推荐单位](/5pic.jpg "img")

## More [TODO]

# js代码
```js
option1 = {
backgroundColor: '#6c343c',

title: {
text: '籍贯分布不完全统计',
left: 'center',
top: 20,
textStyle: {
color: '#ccc'
}
},

tooltip : {
trigger: 'item',
formatter: "{a} <br/>{b} : {c} ({d}%)"
},

visualMap: {
show: false,
min: 80,
max: 600,
inRange: {
colorLightness: [0, 1]
}
},
series : [
{
name:'访问来源',
type:'pie',
radius : '55%',
center: ['50%', '50%'],
data:[
{value:7, name:'安徽'},
{value:12, name:'江苏'},
{value:12, name:'浙江'},
{value:8, name:'湖北'},
{value:7, name:'湖南'},
{value:5, name:'山东'},
{value:5, name:'四川'},
{value:5, name:'辽宁'},
{value:4, name:'河南'},
{value:4, name:'上海'},
{value:6, name:'美籍'},
{value:4, name:'福建'},
{value:3, name:'河北'},
{value:2, name:'重庆'},
{value:2, name:'江西'}
].sort(function (a, b) { return a.value - b.value; }),
roseType: 'radius',
label: {
normal: {
textStyle: {
color: 'rgba(255, 255, 255, 0.3)'
}
}
},
labelLine: {
normal: {
lineStyle: {
color: 'rgba(255, 255, 255, 0.3)'
},
smooth: 0.2,
length: 10,
length2: 20
}
},
itemStyle: {
normal: {
color: '#000000',
shadowBlur: 200,
shadowColor: 'rgba(0, 0, 0, 0.5)'
}
},

animationType: 'scale',
animationEasing: 'elasticOut',
animationDelay: function (idx) {
return Math.random() * 200;
}
}
]
};






option2 = {
title: {
text: '推荐单位统计',
subtext: '数据'
},
tooltip: {
trigger: 'axis',
axisPointer: {
type: 'shadow'
}
},
legend: {

},
grid: {
left: '3%',
right: '4%',
bottom: '3%',
containLabel: true
},
xAxis: {
type: 'value',
boundaryGap: [0, 0.01]
},
yAxis: {
type: 'category',
data: ['复旦大学','上海交通大学','北京大学',
'中国科学技术大学','清华大学','南京大学','中南大学','浙江大学'
,'哈尔滨工业大学','同济大学','中国科学院上海生命科学研究院','中航商用航空发动机有限责任公司','西安交通大学',
'上海交通大学','华东理工大学','中山大学','华中科技大学','四川大学','大连理工大学']
},
series: [

{
name: '推荐单位统计',
type: 'bar',
data: [138, 33, 28, 31, 17, 10,8,13,8,11,8,6,6,6,5,5,6,5,5]
}
]
};






var  option = {
title : {
text: '姓氏统计',
subtext: '选取了数量较多的几种姓氏',
x:'center'
},
tooltip : {
trigger: 'item',
formatter: "{a} <br/>{b} : {c} ({d}%)"
},
legend: {
orient: 'vertical',
left: 'left',
data: ['王','李','张','陈','刘','徐','黄','周','赵','杨','孙','朱','吴','肖','马','陆',]
},
series : [
{
name: '访问来源',
type: 'pie',
radius : '55%',
center: ['50%', '60%'],
data:[
{value:43, name:'王'},
{value:34, name:'李'},
{value:29, name:'张'},
{value:28, name:'陈'},
{value:28, name:'刘'},
{value:16, name:'徐'},
{value:16, name:'黄'},
{value:15, name:'周'},
{value:13, name:'赵'},
{value:12, name:'杨'},
{value:11, name:'孙'},
{value:10, name:'朱'},
{value:9, name:'吴'},
{value:8, name:'肖'},
{value:7, name:'马'},
{value:6, name:'陆'},
],
itemStyle: {
emphasis: {
shadowBlur: 10,
shadowOffsetX: 0,
shadowColor: 'rgba(0, 0, 0, 0.5)'
}
}
}
]
};
```
