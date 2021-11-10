# 目前接口返回网站未备案，但是功能一切正常使用！
学业繁忙，以后再修，感谢使用！届时会推出我在使用的
![752568F9-DED3-4B39-AE91-A421B4AC0905.jpeg](https://i.loli.net/2021/11/10/W1Z2KTzU6xtJfyc.jpg)

各位要加油啊！
# 学习通图书馆座位远程操作API

超星学习通图书馆座位落座、抢座、暂离、取消等api接口

你可以使用siri快捷指令，实现嘴动落座、退座，或是使用python等编程语言自动退座、落座，亦可以制作html、php实现网页远程落座。当然，你也可以用程序定时抢座！

## 接口使用案例

https://cx_api.ssss.men/cxapi?active_id=此处填写命令见下方选项及说明&username=此处填写学习通手机号码(目前不支持学号登陆)&passwd=此处填写密码

  <details>
  <summary> 详细使用案例及相应说明</summary>
  比如我的手机号码为19541817688，我的密码为ilovesunn，我要执行的命令为落座（active_id=sign），所以我应该访问的网址是

  https://cx_api.ssss.men/cxapi?active_id=sign&username=19541817688&passwd=ilovesunn

  同样的，如果我想要预约第二天的座位(active_id=rob)，我要访问的网址为

  https://cx_api.ssss.men/cxapi?active_id=rob&username=19541817688&passwd=ilovesunn
  </details>


## 选项及说明

active_id=sign                        表明落座

active_id=signback                表明退座

active_id=leave                      表明暂离座位

active_id=cancel                    表明取消座位

active_id=rob                         表明预约第二天座位

active_id=rob1                        表明预约今天的座位


username=学习通账号（仅支持手机号登陆）

passwd=学习通密码

## 关于抢座

抢座只会获取历史最近一次预约的座位信息(包括预约时间段、预约座位号码等)，并对照该座位信息预约  第二天(active_id=rob)或今天(active_id=rob1)  的座位

注意：抢座时请在规定时间内执行本程序，否则会触发非法预约（接口返回'Your reservation is illegal'）。有封号的风险！
   <details>
   <summary> 预约座位实例</summary>
   比如，您的学习通账号内最近预约的座位号是110，预约时间段是7:00-10:00，那么本程序预约的座位号也是110，预约时间也还是7:00-10:00

   当访问的网址内active_id=rob时，您的账号将自动预约第二天的座位；当访问的网址内active_id=rob1时，您的账号将自动预约今天的座位；但也应遵守学校的允许预约的时间段，否则就会触发非法预约。有以下两种情况可以借鉴：


1.您的学校在晚上八点后可以预约第二天的座位，如果您想预约第二天的座位，那么您可以在今晚八点定时访问这样的网址https://cx_api.ssss.men/cxapi?active_id=rob&username=此处填入学习通账号&passwd=此处填入密码

2.您的学校在早上七点后可以预约今天的座位，如果您想预约今天的座位，那么您可以在今早七点定时访问这样的网址https://cx_api.ssss.men/cxapi?active_id=rob1&username=此处填入学习通账号&passwd=此处填入密码

注意上述网址中一个active_id为'rob'另一个为'rob1'

当然定时访问网址的操作可以使用计算机程序执行
  
   </details>

### 抢座接口返回
```
{'sucess': False, 'msg': 'This seat has been occupied by others!'} 
```
表明该座位已被他人占用，因此您无法预约该座位
```
{'sucess': False, 'msg': 'You already have a reservation for this time period, so please change to another time!'}
```
表明您在这个时间段已经有预约了，无法再次预约座位
```
{'sucess': False, 'msg': 'Your reservation is illegal, maybe cause the Reservation Time is not advent!'} 
```
表明非法预约！可能因为预约时间还没有到，请注意抢座只会获取您使用账号的历史最近一次预约的座位信息(包括预约时间段、预约座位号码等)

```
{'sucess': True, 'msg': 'Reservation is successful!'}
```
预约成功！


## 其他动作接口返回

```
{'sucess': False, 'msg': 'Unknown error, failed!'}
```
表明未知错误，您可以提交issue帮助我们解决问题
```
{'sucess': False, 'msg': 'You are not currently seated and cannot leave your seat!'}
```
表明您现在还没有座位，因此无法进行暂离座位
```
{'sucess': False, 'msg': 'You have already been seated and cannot be seated again!'}   
```
表明您已经落座了，无法再次落座
```
{'sucess': False, 'msg': 'Seating is not possible before the seat time is up!'}    
```
表明预约的落座时间还未到，需要待落座时间到了才能落座
```
{'sucess': False, 'msg': 'You don't have a seat yet and cannot sign/signback/leave/cancel!'}
```
表明您还没有座位，无法落座/退座/暂离/取消
```
{'sucess': True, 'msg': 'sign/signback/leave/cancel success!'}   
```
表明落座/退座/暂离/取消 操作成功


## IOS用户快捷指令

可以使用siri进行学习通图书馆座位的落座、退座、暂离等功能

网址：[https://sharecuts.cn/shortcut/10733](https://sharecuts.cn/shortcut/10733)

## 简单的html网页

填写学习通账号（仅支持手机账号）、学习通密码，点击'点我签到'按钮即可进行远程签到

网址：[https://qd.ssss.men/](https://qd.ssss.men/)




## 注意

本接口的开发初始目的——为仅使用老人机的同学提供公平的学习环境，请勿商用！




