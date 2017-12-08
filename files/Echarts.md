# Echarts

### 直方图：20171208  BBB案件 30分钟图

```html
app.title = '坐标轴刻度与标签对齐';

option = {
    color: ['#3398DB'],
    tooltip : {
        trigger: 'axis',
        axisPointer : {            // 坐标轴指示器，坐标轴触发有效
            type : 'shadow'        // 默认为直线，可选为：'line' | 'shadow'
        }
    },
    grid: {
        left: '3%',
        right: '4%',
        bottom: '3%',
        containLabel: true
    },
    xAxis : [
        {
            type : 'category',
            data : ['00:00-00:30','00:30-01:00','01:00-01:30','01:30-02:00','02:00-02:30','02:30-03:00','03:00-03:30','03:30-04:00','04:00-04:30','04:30-05:00','05:00-05:30','05:30-06:00','06:00-06:30','06:30-07:00','07:00-07:30','07:30-08:00',],
            axisTick: {
                alignWithLabel: true
            }
        }
    ],
    yAxis : [
        {
            type : 'value'
        }
    ],
    series : [
        {
            name:'surge',
            type:'bar',
            barWidth: '60%',
            data:[10, 52, 200, 334, 390, 330,10, 52, 200, 334, 390, 330,10, 52, 200, 334]
        }
    ]
};

```

http://echarts.baidu.com/demo.html#bar-tick-align





