# Yuki-Glados-Checkin
Glados VPN Checkin

通过 github action 来实现自动签到，每天签到可以延时一天。

但是当签到一定次数后，将会返回 `Checkin! Get 0 day(Your lucky chance is 33%), try next time.`，大概意思就是 1/3 的几率获得 1 天的奖励。

[GLaDOS 官方 github](https://github.com/glados-network/GLaDOS)，[GLaDOS 官网](https://glados.rocks/)。

如果还没有注册的话，可以去[这里](https://glados.rocks/register)注册，然后填写邀请码：`0HCLD-0XA70-YBI10-Z6836`。双方都可以获得奖励天数哦。

## 步骤

### 1 fork 这个仓库

点击右上角的 fork。

### 2 获取 身份信息

在 [GLaDOS](https://glados.rocks/console/checkin) 的网页上按 F12，如下图~

![image](https://user-images.githubusercontent.com/53206696/212589322-9c374fbe-1aff-4598-9743-e3703bc1538b.png)

### 3 设置 身份信息

拿到koa:sess.sig与koa:sess的值， 在github 设置中， 如下图

![image](https://user-images.githubusercontent.com/53206696/212588583-0ba7d00a-4b06-4b59-9a2a-6ba7605acbf1.png)

### 4 运行 

随便发起一个 push 请求，可以修改一下 `README.md`，或者自己给自己点个 star，就可以开始。之后就会每隔 6 小时进行一次签到（因为有时候签到会失败，好像是服务器不太好，就设置一下每小时签到一次保证成功吧）。

注意，在官方文档中有这么一段：

> To prevent unnecessary workflow runs, scheduled workflows may be disabled automatically. When a public repository is forked, scheduled workflows are disabled by default. In a public repository, scheduled workflows are automatically disabled when no repository activity has occurred in 60 days.

也就是说，**定时执行的任务需要每隔 60 天激活一次**。
