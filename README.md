# corpredit
crawler of the campany redit infomation

预计目标：爬取信用信息公示系统中指定企业的信用相关信息

实际目标：绕过反扒，同时结合requests包和cookie信息进一步进行请求，从而获得相关信息。

反爬系统：加速乐+极验验证码（滑动或文字点击）

主要使用包：selenium,chromdriver,requests,cv2,numpy,PIL,lxml

思路：

1、请求2次加速乐验证网址，第一遍获取gt和challenge的cookie，第二遍带cookie访问。

2、请求首页网址。

3、定位输入框，输入关键字查询。

4、定位验证框，根据验证码类型确定选用点击验证程序还是滑动验证程序。

5、如果是点击验证程序，将其验证框截图发送至打码平台（此处选用超级鹰）。

6、如果是滑动验证程序，则自己编写程序操控鼠标拖动破解。

7、破解失败的化自动重新破解，直至破解成功或者破解失效直接退出。

8、破解成功后，保存查询结果，同时保存cookie。

9、解析查询结果页面，提取出每一条结果的网址。

10、使用request，通过添加cookies，实现模拟请求每一条结果页面。

11、解析最终结果页面，获取基本信息。


备注：

1、本文中的程序仅演示获取部分数据，获取完整数据及存储不是本程序重点
程序重点在如何设计验证过程中出现的各种问题及其应对措施。

2、本程序有比较详细的程序解释信息，方便阅读。
