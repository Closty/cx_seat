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

active_id=rob                         表明抢座（暂时无法使用，请等待更新）

username=学习通账号（仅支持手机号登陆）

passwd=学习通密码

本接口仅能使用http的80端口，暂时无法使用https的443端口

## 接口返回

```json
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

其实，抢座的脚本已经开发完毕了，但害怕使用的人数太多会被封掉而自己每天确实需要去图书馆，目前没有开放API的想法。请原谅我的自私

但是如果你真的需要使用抢座脚本，我可以帮你挂上，5元/月吧，大概就是服务器成本

前提是你真的，真的，真的需要每天去图书馆，否则请勿联系！请谅解！

网址：[https://ssss.men](https://ssss.men)

## 注意

本接口的开发初始目的——为仅使用老人机的同学提供公平的学习环境，请勿商用！
