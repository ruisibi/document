# 通过单点登录实现BI系统和其他系统的整合

睿思BI系统有自己一套登录，用户，角色管理模块，也可以通过单点登录功能和用户已有系统实现整合，整合步骤如下：

1.用户的系统提供Rest接口，BI系统通过此接口获取用户信息，接口返回信息如下:

```
{"userId":1,"staffId":"admin","loginName":"系统管理员","gender":"女","state":1,"deptCode":"002"}
```

其中：userId 用户ID最重要, ID 必须是数字类型。

2.把此接口配置到 bi 系统的application.properties配置文件中，如下图:

```
################################sso 配置信息 ###############################################
#根据登录账号获取用户信息，可不配
sso.url.userInfo.bystaff=
#根据TOKEN获取用户信息，必须配置
sso.url.userInfo.bytoken=http://localhost:8082/rsbi/resource/user.json
#获取需要整合系统的用户列表，可不配
sso.url.userList=
```

3.通过 [http://localhost:8082/rsbi/frame/Frame.action?rsbiToken=abc](http://localhost:8082/rsbi/frame/Frame.action?rsbiToken=abc) 方式直接访问BI系统，其中 rsbiToken 是BI系统用来验证登陆的token，此token会被传递到sso.url.userInfo.bytoken中配置的接口中，用户提供接口需要实现按此token返回用户信息，如果用户不存在直接返回空。如果token信息无误，只要在BI系统的URL后面增加rsbiToken=abc参数，即可实现自动登录。

4.如果用户系统注销登录，需要调用bi系统的 [http://localhost:8082/rsbi/frame/Logout.action](http://localhost:8082/rsbi/frame/Logout.action) 接口注销BI系统的登录信息。

