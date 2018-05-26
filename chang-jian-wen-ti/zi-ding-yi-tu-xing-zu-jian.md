# 自定义图形组件

睿思BI系统中所有图形组件都定义在ext-config.xml中。图形组件都实现 com.ruisi.ext.engine.view.emitter.chart.ChartEmitter 接口，配置信息如下:

```
<chart shape="line" class="com.ruisi.ext.engine.view.emitter.chart.echarts.LineChart"/>
<chart shape="area" class="com.ruisi.ext.engine.view.emitter.chart.echarts.AreaChart"/>
<chart shape="bar" class="com.ruisi.ext.engine.view.emitter.chart.echarts.BarChart"/>
<chart shape="bubble" class="com.ruisi.ext.engine.view.emitter.chart.echarts.BubbleChart"/>
<chart shape="column" class="com.ruisi.ext.engine.view.emitter.chart.echarts.ColumnChart"/>
<chart shape="gauge" class="com.ruisi.ext.engine.view.emitter.chart.echarts.GaugeChart"/>
<chart shape="map" class="com.ruisi.ext.engine.view.emitter.chart.echarts.MapChart"/>
<chart shape="nestingPie" class="com.ruisi.ext.engine.view.emitter.chart.echarts.NestingPieChart"/>
<chart shape="pie" class="com.ruisi.ext.engine.view.emitter.chart.echarts.PieChart"/>
<chart shape="radar" class="com.ruisi.ext.engine.view.emitter.chart.echarts.RadarChart"/>
<chart shape="scatter" class="com.ruisi.ext.engine.view.emitter.chart.echarts.ScatterChart"/>
<chart shape="scatterMap" class="com.ruisi.ext.engine.view.emitter.chart.echarts.ScatterMapChart"/>
```

创建自定义图形组建过程如下:

1.继承 AbstractChartEmitter 类并实现ChartEmitter接口，如下：

```java
package com.ruisi.ext.engine.view.emitter.chart;

import javax.servlet.jsp.JspException;

public class TestChart extends AbstractChartEmitter implements ChartEmitter  {

public int createChartJS(boolean toPic) throws JspException {

    return 0;
}

}
```

2.把创建的类配置到 ext-config.xml 文件中。

```
<chart shape="test" class="com.ruisi.ext.engine.view.emitter.chart.echarts.TestChart"/>
```

其中sharp 配置图形标识，class 配置图形类。

3.在报表，多维的js中添加 shape 为 test 的图形组件。

通过更改图形class类实现，也能更改系统的基础图形。

