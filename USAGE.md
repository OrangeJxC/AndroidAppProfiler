# Android App Profiler

![screenshot](/Images/screenshot.jpg)
<br/>
<br/>
<br/>
AppProfiler是一个类似于Perfdog的Android App性能跟踪工具， 用来跟踪Android App的FPS、CPU、GPU、内存和电池相关的信息。方便评估App运行时的资源占用和性能表现，以及评估Android设备的硬件性能。

<br/>
<p>收集的的数据:</p>

![screenshot](/Images/cd.jpg)



## 使用方法

### PC端
1. 从本项目最新的Releases下下载AndroidAppProfiler.zip， 下载完成之后解压到任意文件夹内。
2. 运行AppProfiler.exe。
3. 打开Android设备的[开发者选项](https://developer.android.com/studio/debug/dev-options?hl=zh-cn)，在开发者选项中打开调试模式, 通过USB线将设备连接到PC, 或使用[无线调试模式](https://cloud.tencent.com/developer/article/1809910)
4. 在AppProfiler中选择对应的设备和要跟踪的App, 点击开始按钮就开始跟踪数据了。
 
   ![](/Images/o1.jpg)
   
5. 在跟踪过程中可以点击暂停或停止按钮来暂停或停止当前的跟踪。
 
     ![](/Images/o5.jpg)
   
6. 停止跟踪之后会显示当前跟踪部分数据的平均、最大、最小值。
7. 根据的数据保存AppProfiler.exe相同文件夹下的ProfileData文件夹下。按照App名称->跟踪开始时间->数据类型分类。
8. 滑动曲线图右上方的滑块可以横向缩放曲线。
 
    ![](/Images/o2.jpg)
   
9. 鼠标移动到曲线图范围内会显示当前这秒的数据。
   
   ![](/Images/o4.jpg)
   
10. 点击右上方的两个按钮分别在资源管理器中打开保存数据的文件夹和打开当前使用教程。

    ![](/Images/o3.jpg)

### Android端

1. 设备第一次跟踪时会安装文件夹下的PerfMonitor.apk，若安装失败可以手动安装。
2. App安装成功之后，需要申请悬浮窗权限，要在Android设备上显示相关数据请给与App权限。
3. 在跟踪时会检查该App是否运行，若没有运行的则会启动该App，若要持续在悬浮窗显示数据需要Android保持亮屏状态。
4. App启动之后只会显示一个悬浮窗口，没有别的界面。悬浮窗口会同步显示当前收集的部分数据。

    ![](/Images/f1.jpg)

5. 点击悬浮窗右上角的按钮可以设置要显示哪些些数据。

    ![](/Images/fw2.jpg)

6. 悬浮窗至少保留显示当前FPS的数据。

    ![](/Images/fw3.jpg)
7. 关闭悬浮窗或退出应用
   <br/>
   为了防止误触，悬浮窗上没有关闭按钮。正常情况下关闭PC端应用会退出该App, 若没有退出可以点击App通知上的停止按钮来退出应用，或在多任务界面结束该App运行。

## 注意事项

- 不要修改文件夹内的文件的名称, AppProfiler.exe内是以相对路径使用的，修改了可能无法正常跟踪。
- PerfMonitor App非必须安装。若不安装或跟踪中不运行该App，或设备熄屏，某些设备可能无法读取部分数据。
- 该程序目前只适配了高通GPU,非高通GPU的设备无法读取到GPU的使用率和频率。由于不同品牌，型号的系统权限设置不同，某些高通GPU的设备上也无法读取到GPU的当前频率。
- 若要跟踪相对比较准确的电池功率，请使用无线连接或无线调试模式。   

## 常见问题

- 数据准确性问题
   <br/>
   由于统计时间节点和数据来源可能与其它跟踪程序的不一致，收集的数据不可能与其他程序的数据完全一致，只能尽量保证一致或减少误差，本程序所有收集的数据仅供参考。
- 数据标准
   <br/>
   本程序收集的绝大部分数据都是按照行业内的默认标准收集计算。FPS的卡顿统计逻辑与[PerfDog的标准](https://perfdog.qq.com/article_detail?id=10162&issue_id=0&plat_id=1)一致。
- 数据安全性和隐私
    <br/>
   PC端程序及Android端App都没有连接互联网，收集的数据都存放在设备中, 没有将任何数据上传到其它地方。
- 关于adb文件夹
   <br/>
   项目下的adb文件夹内是Android设备的调试工具:[adb](https://developer.android.com/tools/adb?hl=zh-cn)。是由Android开发平台提供的程序。AppProfiler运行必须依赖该程序。
- 兼容性问题
   <br/>
   AppProfiler.exe基于WPF架构开发，理论上支持Windows7及以上的系统。PerfMonitor App支持Android 8.0及以上的系统。
   这两个程序经过测试的设备数量非常有限，可能在某些设备上程序无法运行、无法收集到某些数据、或收集到的数据误差较大。这些都需要慢慢适配。遇到问题可以在本项目中提Issue。
- 代码开源
   <br/>
   由于该程序还在初步开发阶段，而且开始在Windows平台的开发时间较短，后面还有大量的可优化、完善的工作，所以暂时没有开源的计划。
- 问题跟踪
   <br/>
   PC端程序在运行过程中会输出一些错误和数据到log中，log保存在文件夹下logs文件夹下。每次跟踪的关键数据也会写入到对应的跟踪目录下面。方便后面发现问题。日志经过控制，不会占用很多的硬盘空间。


   
   
