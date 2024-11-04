# J-Calendar
墨水屏日历，采用三色4.2寸墨水屏，展示基本月历信息，支持农历、公共假期、倒计日展示。<br>
注：个人可免费下载固件使用，禁止商用。

## Prepare & Meterial
1. esp32开发板(建议lolin32 lite,其他esp32开发板亦可)
2. 4.2寸三色墨水屏(400*300)。
3. 墨水屏驱动板。
4. 锂电池,需要做ph2.0接头。(建议603048, 900mah)
5. 金属底座亚克力台卡,95*80mm。
6. 轻触开关,(12*12*7.3,带键帽)
7. 工具:电烙铁、电线若干。

## Manufacture Guide:
1. 接线
    * Busy->4
    * RST->16
    * DC->17
    * CS->5
    * SCK->18
    * SDA->23
    * GND->GND
    * VCC->3V
    * LED->22(板载)
2. 三色墨水屏排线插入时注意针脚方向,屏幕排线和驱动板排线1号针脚均是悬空,注意对齐。
3. 电池接口需要是ph2.0,且注意正负极(开发板上有标注),如果电池的正负极反了,可以用镊子调整电池插头。

## Button Operation Guide:
1. **单点**  
    如果处在休眠中,唤醒系统
2. **双击**  
    系统正常运行中,双击进入系统配置。  
    系统配置状态中,双击重启系统。
3. **长按**  
    系统运行中,长按清除配置信息(WIFI密钥除外)和缓存,并重启。

## LED Indicator: 
(板载LED,PIN-22)
1. 快闪:系统启动中,正在连接WIFI
2. 常亮:WIFI连接完成(成功或失败)
3. 三短闪一长灭:系统配置中。
4. 熄灭:系统休眠。

## Web Config Guide:
通过在开机状态下(LED常亮)双击,即可进入配置状态,这时系统会生成一个名为J-Calendar的ap,默认密码为:password。(默认超时时间为180秒)
连接上ap后会直接弹出配置页面。(或者直接通过浏览器输入地址 http://192.168.4.1进入)。
配置页面:
1. Config Wifi. Wifi配置  
    进入配置wifi页面,选择搜索到的ap,并输入密码,并保存。
2. Setup. 系统配置  
    和风天气:输入和风天气的token和城市id(城市对应的id请在和风天气的官网查找。)系统会每2小时刷新当前天气,如果token置空,天气将不会被刷新,系统每日凌晨0点刷新日历。  
    倒数日:输入倒数日名称和日期,名称不能超过4个中文字符,时间以yyyyMMdd的格式填入。配置正确的话,日历每天会显示倒数“距****还有**天”。如果倒数日名称为空,系统将不显示倒数日信息。
3. Update. OTA升级  
    此项需要在浏览器内完成,通过ip地址访问配置页面,然后进入Update,选择固件文件后上传,等待。刷新完成后,页面会有成功提示。
4. Restart. 重启  
    在所有配置完后,需要重启生效。(也可以在配置状态下,双击按钮重启)
5. Info. 系统信息  
    可以监控系统的硬件情况,也可以在里面清除配置的Wifi密钥。
6. Exit. 退出  
    退出配置状态。

## Reference:
1. \<WEMOS LOLIN32簡介\> https://swf.com.tw/?p=1331&cpage=1
2. \<GxEPD2\> https://github.com/ZinggJM/GxEPD2
3. \<U8g2_for_Adafruit_GFX\> https://github.com/olikraus/U8g2_for_Adafruit_GFX
4. \<和风天气\> https://dev.qweather.com/docs/api/weather/weather-now/

<br>
<br>
 Copyright © 2022-2024 JADE Software Co., Ltd. All Rights Reserved.

