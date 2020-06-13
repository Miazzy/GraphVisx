# GraphVis

### 目前开源的部分核心可视化库和布局算法库，后续会开源基于该组件的应用示例，如话单分析、社交网络分析等方面的应用。

主页：[图说数据 www.graphvis.cn](http://www.graphvis.cn)

开发文档：[组件开发文档 www.graphvis.cn](http://www.graphvis.cn/graph/dev-doc/index.html)

GitHub:[GitHub地址](https://github.com/dubaopeng/GraphVis)

专注于关系网络数据可视化分析，适用于复杂网络可视分析，知识图谱可视化，网络拓扑图，关系图等场景应用。

1. 支持丰富的可视化效果，多种节点样式，连线样式等
2. 支持多种布局算法，如：树形结构类，力导向布局类，圆形类，放大缩小、旋转、节点避免重叠等
3. 支持常见经典社区划分算法，如：chineseWisper, lovin等

```
开发文档会持续进行完善，同时会开放一些基于该组件开发的应用实例，方便开发人员学习使用。
欢迎有兴趣的同学们参与进来，共同把GraphVis打造成为图数据可视化分析领域的流行组件。
```

### 快速使用

```
界面原生方式引用
当前组件包支持两种引用方式：

页面标签直接引用
<script type="text/javascript" src="../visgraph-x.x.x.min.js"></script>

require异步加载引用 页面标签直接引用
requirejs(['visgraph','layoutFactory','clusterFactory'],function(VisGraph,layoutFactory,clusterFactory) {//do something});

```

#### GraphVis实现图数据的可视化只需以下三步即可，无需深入的基础知识也可快速使用：

```
1、后台服务按照格式组织数据，如：
var data = {
   nodes:[{id:'1',label:'刘备',type:'男',properties:{age:50}},
         {id:'2',label:'关羽',type:'男'},
         {id:'3',label:'张飞',type:'男'}],
   links:[{source:'1',target:'2',label:'二弟'},
         {source:'1',target:'3',label:'三弟'}]
};

2、界面添加图层包裹元素，如：
<div id="graph-panel" style="width:800px;height:600px;"></div>

3、初始化关系图
let visGraph = new VisGraph(document.getElementById(visDomId));
visgraph.drawData(data);//绘制图完成

```

#### 支持自定义配置，实现个性化需求及交互
```
详细配置如下,可选择性配置需要的参数，不需要无需配置
let visGraph = new VisGraph(document.getElementById(visDomId),
    {
        node:{ //节点的默认配置
            label:{ //标签配置
                show:true, //是否显示
                color:'50,50,50',//字体颜色
                font:'12px 微软雅黑',//字体大小及类型
                wrapText:false, //节点包裹文字
                textPosition:'Middle_Center'//文字位置 Top_Center,Bottom_Center,Middle_Right
            },
            shape:'circle',//节点形状 circle,rect,ellipse,triangle,star,polygon,text
            color:'20,20,200',//节点颜色
            borderColor:'255,255,20',//边框颜色
            borderWidth:0,//边框宽度,
            showShadow:true,//显示选中阴影
            shadowColor:'0,255,0',//阴影颜色
            alpha:1,//节点透明度
            size:60, //节点默认大小
            onClick : function(event,node){ //节点点击事件回调
                // do something
                console.log('click node----['+node.id+':'+node.label+']');
            }
        },
        link:{ //连线的默认配置
            label:{ //连线标签
                show:false, //是否显示
                color:'20,20,20', //字体颜色
                font:'11px 微软雅黑'//字体大小及类型
            },
            lineType:'direct',//连线类型,direct,curver,vlink,hlink,bezier,vbezier,hbezier
            colorType:'defined',//连线颜色类型 source:继承source颜色,target:继承target颜色 both:用双边颜色，defined:自定义
            color:'180,180,180', //连线颜色
            alpha:1,  // 连线透明度
            lineWidth:5, //连线宽度
            lineDash:[0],//虚线间隔样式如：[5,8]
            showArrow:true,//显示箭头
            onClick :function(event,link){ //连线点击事件回调
                // do something
                console.log('click link---['+link.source.id+'-->'+link.target.id+']');
            }
        },
        highLightNeiber:true, //相邻节点高度标志
        backGroundType:'png',//保存图片的类型，支持png、jpeg
        wheelZoom:0.8,//滚轮缩放开关，不使用时不设置[0,1]
        marginLeft:-40, //对右键菜单位置进行调校的参数
        rightMenu:{
            nodeMenu:NodeRightMenu,  //节点右键菜单配置
            linkMenu:LinkRightMenu   // 连线右键菜单配置
        }
    }
);
```

## 应用效果截图

## 知识图谱可视化
![图谱应用1](http://media.graphvis.cn/tupuvis.png)
![图谱应用2](http://media.graphvis.cn/zishitupu.png)
![复杂网络可视化效果](http://media.graphvis.cn/second2.png)
![复杂网络可视化效果2](http://media.graphvis.cn/tupuvis2.png)
![网络拓扑结构](http://media.graphvis.cn/three-scnece-bg.png)
![网络拓扑结构](http://media.graphvis.cn/secondbg.png)

## GraphVis 交流讨论
<img src="http://media.graphvis.cn/QQ-ercode.jpg" width = "180" height = "300" alt="" align=center />
<img src="http://media.graphvis.cn/wxerCode.png" width = "180" height = "300" alt="" align=center />

