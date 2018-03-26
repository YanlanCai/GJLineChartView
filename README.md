# GJLineChartView
支持显示折线图、柱状图、饼状图。其中折线图可以伸缩并长按显示数据，柱状图也可以长按显示数据。

### 导入项目
- 你可以直接下载后拖进项目使用；
- 也可以使用cococpods；
```
pod search GJLineChartView
```
```
pod 'GJLineChartView', '~> 1.0.0'
```

### 使用
**折线图**
```
NSArray *XTitleArray = [NSArray arrayWithObjects:@"08:36",@"08:39",@"08:42",@"08:45",@"08:48",@"08:51",@"08:54",@"08:57",@"09:00",@"09:03",@"09:06",@"09:09",@"09:12",@"09:15",@"09:18",@"09:21",@"09:24",@"09:27",@"09:30",@"09:33",@"09:36",@"09:39",@"09:42",@"09:45",@"09:48",@"09:51",@"09:54",@"09:57",@"10:00",@"10:03",@"10:06",@"10:09",@"10:12",@"10:15",@"10:18",@"10:21",@"10:24",@"10:27",@"10:30",@"10:33",@"10:36",@"10:39",@"10:42",@"10:45",@"10:48",@"10:51",@"10:54",@"10:57",@"11:00",@"11:03",@"11:06",@"11:09",@"11:12",@"11:15",@"11:18",@"11:21",@"11:24",@"11:27",@"11:30",@"11:33",@"11:36",@"11:39",@"11:42",@"11:45",@"11:48",@"11:51",@"11:54",@"11:57",@"12:00",@"12:03",@"12:06",@"12:09",@"12:12",@"12:15",@"12:18",@"12:21",@"12:24",@"12:27",@"12:30",@"12:33",@"12:36",@"12:39",@"12:42",@"12:45",@"12:48",@"12:51",@"12:54",@"12:57",@"13:00",@"13:03",@"13:06",@"13:09",@"13:12",@"13:15",@"13:18",@"13:21",@"13:24",@"13:27",@"13:30",@"13:33",@"13:36",@"13:39",@"13:42",@"13:45",@"13:48",@"13:51",@"13:54",@"13:57",@"14:00",@"14:03",@"14:06",@"14:09",@"14:12",@"14:15",@"14:18",@"14:21",@"14:24",@"14:27",@"14:30",@"14:33",@"14:36",@"14:39",@"14:45",@"14:48",@"14:51",@"14:54",@"14:57",@"15:00",@"15:03",@"15:06",@"15:09",@"15:12",@"15:15",@"15:18",@"15:21",@"15:24",@"15:27",@"15:30",@"15:33",@"15:36",@"15:39",@"15:42",@"15:45",@"15:48",@"15:51",@"15:54",@"15:57",@"16:00",@"16:03",@"16:06",@"16:09",@"16:12",@"16:15",@"16:18",@"16:21",@"16:24",@"16:27",@"16:30",@"16:33",@"16:36",@"16:39",@"16:42",@"16:45",@"16:48",@"16:51",@"16:54",@"16:57",@"17:00",@"17:03",@"17:06",@"17:09",@"17:12",@"17:15",@"17:18",@"17:21",@"17:24",@"17:27",@"17:30",@"17:33",@"17:36",@"17:39",@"17:42",@"17:45",@"17:48",@"17:51",@"17:54",@"17:57", nil];
    NSArray *YValueArray = [NSArray arrayWithObjects:@"22.5",@"23.1",@"27",@"31.7",@"32.9",@"31.1",@"27.2",@"25.1",@"23.2",@"23.3",@"25.2",@"24.8",@"24.7",@"26.6",@"26",@"26",@"26.3",@"26.2",@"26.5",@"30.2",@"32.3",@"35",@"36.7",@"37.5",@"38.1",@"36.6",@"34.5",@"35.5",@"36",@"34.4",@"33.8",@"33.6",@"33.5",@"32.4",@"30.2",@"30",@"28.9",@"27.5",@"26.9",@"27.4",@"27.2",@"27.1",@"24.6",@"22",@"22.2",@"21.2",@"22.3",@"24.5",@"23.6",@"23.4",@"23.7",@"23.8",@"22.8",@"23.1",@"23.8",@"22.8",@"22.1",@"23.6",@"23.5",@"22",@"19.2",@"17.3",@"17.5",@"16",@"15",@"15.4",@"16.1",@"15.6",@"15.3",@"16",@"16.5",@"16.2",@"17.4",@"19.2",@"19.5",@"21.3",@"23.1",@"23.5",@"21",@"20.3",@"18.2",@"18.8",@"20.3",@"20.1",@"19.9",@"21.6",@"21.4",@"20.8",@"19.2",@"17.9",@"16.3",@"15.3",@"15.7",@"15.4",@"15",@"14.5",@"14.4",@"14.3",@"14",@"13.7",@"13.2",@"12.5",@"12",@"11.7",@"11.5",@"11.6",@"11.7",@"11.2",@"10.9",@"10.8",@"10.5",@"10.1",@"9.8",@"8.5",@"8.3",@"8.6",@"9.1",@"9.3",@"8.9",@"8.6",@"8.1",@"8.1",@"7.5",@"6.7",@"6.9",@"6.9",@"6.7",@"6.5",@"6.6",@"6.2",@"6.4",@"7",@"7.1",@"7",@"6.4",@"5.4",@"4.9",@"4.8",@"4.8",@"4.6",@"4.5",@"4.5",@"4.6",@"4.6",@"4.7",@"4.6", nil];
    GJLineChartView *lineChartView = [[GJLineChartView alloc] initWithFrame:CGRectMake(0, 100, self.view.frame.size.width,self.view.frame.size.height - 300) xTitleArray:XTitleArray yValueArray:YValueArray yMax:38.1 yMin:0.0 unit:@"kWh"];
    [self.view addSubview:lineChartView];
```
**柱状图 && 饼状图**
```
// type：0为饼状图，1为柱状图
    NSArray *XTitleArray = [NSArray arrayWithObjects:@"1",@"2",@"3",@"4",@"5",@"6",@"7",@"8",@"9",@"10",@"11",@"12", nil];
    NSArray *YValueArray = [NSArray arrayWithObjects:@"10",@"23",@"23",@"49",@"30",@"56",@"40",@"20",@"5",@"78",@"65",@"34", nil];
    GJChartDrawView *vc=[[GJChartDrawView alloc]initWithFrame:CGRectMake(0, 100, self.view.frame.size.width,self.view.frame.size.height - 300) type:0 yMax:78 yMin:0];
    vc.arrayPoint  = (NSMutableArray *)YValueArray;
    vc.scaleArray  = (NSMutableArray *)XTitleArray;
    vc.unitStr     = @"kwh";
    [self.view addSubview:vc];
```

### 效果图
![折线图](https://github.com/manofit/GJLineChartView/blob/master/GJLineChartView/%E6%8A%98%E7%BA%BF%E5%9B%BE.png)
![柱状图](https://github.com/manofit/GJLineChartView/blob/master/GJLineChartView/%E6%9F%B1%E7%8A%B6%E5%9B%BE.png)
![饼状图](https://github.com/manofit/GJLineChartView/blob/master/GJLineChartView/%E9%A5%BC%E7%8A%B6%E5%9B%BE.png)
