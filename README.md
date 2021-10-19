# 学习通图书馆座位远程操作API

超星学习通图书馆座位落座、抢座、暂离、取消等api接口

你可以使用siri快捷指令，实现嘴动落座、退座，或是使用python等编程语言自动退座、落座，亦可以制作html、php实现网页远程落座

## 接口使用案例

```json
http://cx_api.ssss.men/cxapi?active_id=sign&username=19541817688&passwd=ilovesunn
```

## 选项及说明

active_id=sign                        表明落座

active_id=signback                表明退座

active_id=leave                      表明暂离座位

active_id=cancel                    表明取消座位

active_id=rob                         表明抢座

username=学习通账号（仅支持手机号登陆）

passwd=学习通密码

本接口仅能使用http的80端口，暂时无法使用https的443端口

## 接口返回

```
{'sucess': False, 'msg': 'You don't have a seat yet and cannot sign!'}
{'sucess': False, 'msg': 'Unknown error, failed!'}
{'sucess': False, 'msg': 'You are not currently seated and cannot leave your seat!'}
{'sucess': False, 'msg': 'You have already been seated and cannot be seated again!'}
{'sucess': False, 'msg': 'Seating is not possible before the seat time is up!'}
{'sucess': False, 'msg': 'You don't have a seat yet and cannot sign/signback/leave/cancel!'}
{'sucess': True, 'msg': 'sign/signback/leave/cancel success!'}
```

## IOS用户快捷指令

可以使用siri进行学习通图书馆座位的落座、退座、暂离等功能

网址：[https://sharecuts.cn/shortcut/10733](https://sharecuts.cn/shortcut/10733)

## 简单的html网页

填写学习通账号（仅支持手机账号）、学习通密码，点击'点我签到'按钮即可进行远程签到

网址：[https://qd.ssss.men/](https://qd.ssss.men/)

## 关于抢座

抢座只会获取最近一次预约的座位信息，并对照该座位信息（包括座位号码以及预约时间段）执行第二天抢座

注意：抢座时请在规定时间内执行本程序，否则会触发非法预约（接口返回'Your reservation is illegal'）。有封号的风险！

```
{'sucess': False, 'msg': 'This seat has been occupied by others!'}
{'sucess': False, 'msg': 'You already have a reservation for this time period, so please change to another time!'}
{'sucess': False, 'msg': 'Your reservation is illegal, maybe cause the Reservation Time is not advent!'}
{'sucess': True, 'msg': 'Reservation is successful!'}
```

## 注意

本接口的开发初始目的——为仅使用老人机的同学提供公平的学习环境，请勿商用！
