# AUICrawler
### 遍历方案
#### 时间模式
* Limit ：限定遍历时长，不包括初始化应用 & 结果统计，超过规定时长后结束
* Free  ：不规定遍历时长，全部递归执行完成后结束
#### 遍历模式
* Normal ： 按序遍历，多次／多设备执行的路径完全相同
* Random ： 随机遍历，可设置覆盖程度（0 <CoverageLever <=1）,在当前页面中随机抽取 覆盖百分比个 控件进行遍历
* Activity ： 遍历App的所有Activity（可无参数唤起的）
### 执行相关
#### 执行前配置
** 配置文件 : **
- AUICrawler
  - script
    - Setting.py
#### 执行脚本
- AUICrawler
  - Crawler.py
#### 执行方案
```
1.  支持多设备同时执行（多线程执行，每个设备单个线程）
2.  初始化App（针对首次启动有需滑动的Guide页的App，优先向左滑动到有可点击的控件显示；会遍历进入主页面前显示的控件至进入Setting中设置的主页面）
3.  支持执行Robotium Case（主要是用来再初始化App至满足想要的遍历条件，比如遍历前先登录 ／ 解决一些可能会影响遍历的操作）
4.  启动主页面按所选模式开始遍历
```
### 脚本结构
#### 封装的模块
##### 所在目录
- AUICrawler
  - module
##### 模块介绍
** PlanInfo :  本次执行的相关配置 & 运行状态等信息 **
** CrawledApp :  当次执行时使用的App本身信息 & 遍历中相关状态&信息 **
** DeviceInfo :  每个执行的Device的本身信息 & 遍历中相关状态&信息 **
** PageInfo :  每次获取时的页面信息 & 遍历中相关状态&信息 **
** NodeInfo :  每个控件的获取时信息 & 遍历中相关状态&信息 **
### 开发进度
```
1. 所需对象架构已设计完成，可随时增删改对象属性 ✅
2. 递归逻辑架构已完成 ✅
3. 各模式的配置信息已设计完成 ✅
4. 各模式的判断&执行框架未完成 ❌
5. 对Clickable的控件遍历框架已完成，按需调试即可 ✅
6. 对LongClickable的控件遍历未实现 ⭕️
7. 对EditText的遍历未实现 ⭕️
8. 对Scrollable的控件的遍历未实现  ⭕️
9. 执行结果收集&统计&展示未设计&实现 ⭕️
10. 遍历过程中，遍历到登录页面登录功能未实现 ⭕️
11. Activity模式的实现方式未调研  ⭕️
12. 命令行执行参数未开始设计&实现 ⭕️
```
