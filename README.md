# 1024(草榴论坛)-Autoreplytest 

因为考研在即，加上1024的回复机制确实有点繁琐，所以打算用个python脚本做一个自动回帖，本脚本主要适用于新手上路到侠客之间 

<h4>使用说明(github Actions方式)</h4>

![Fork位置与Settings位置](https://github.com/0honus0/1024-Autoreply/blob/master/doc/fork%20and%20settings.png)

![Secrets位置](https://github.com/0honus0/1024-Autoreply/blob/master/doc/Secrets.png)

![new secret位置](https://github.com/0honus0/1024-Autoreply/blob/master/doc/new%20Secret.png)
<h4>1.Fork之后，通过settings -> Secrets -> new secret添加下列值</h4>

(必需)

        USER             用户名

        PASSWORD         密码

        SECRET           谷歌身份验证器密钥

(可选1)([申请地址](https://market.aliyun.com/products/57124001/cmapi027426.html))

        TOKER            阿里验证码识别接口AppCode

(可选2)([注册地址](http://ttshitu.com/register.html?inviter=3d92d1b2371f487d9072430a93bb043c) )

        CODEUSER         注册用户名

        CODEPASS         注册密码

ps:可选两个是识别验证码用的，任选其一即可，也可以都不选。如果不选碰见需要验证码的则会运行失败。

       第一个用的是阿里一个api接口，每月30次免费的，正常是够用的

       第二个是自己找的一个平台，1元可以识别500次，因为我最开始需要调试，所以用的这个

代码中使用的就是第二个，如果想要使用第一个，只需修改`1024.py`文件中的`第八行`

`from getver1 import Getver` 为 `from getver import Getver`

<h4>2.(1)先点击Actions,同意使用协议。

(2)然后随便修改任一文件的内容进行一次提交，就可以在Actions里面看见项目运行</h4>

<h4>(可选)3.可以通过`getreply()中的reply与reply_m(0,n)(n设为回复的内容个数-1)`设置回复内容，`sleeptime设置为(1024,2048)之间`，可以根据需要修改。因为Actions一个项目限制6个小时，所以最大值不要超过2048。如果Actions显示运行超过六小时，先自行检查之前是否回复成功，若是，则把2048调整小一点。若不是，请提issues</h4>

<h4>(可选)4.下面是自己下载py文件运行时的问题</h4>

修改以下参数，记得用''括起来

        user=''                 用户名

        password=''             密码

        secret=''               谷歌身份验证器密钥

验证码部分根据自己选择修改参数类似上面

有能力可以自己登陆修改为使用cookies登录，就不需要验证码部分了

有bug反馈下，暂时没时间修，就放之后吧

~~**后继可能添加功能：**(已实现)~~

~~1.修改为github Actions的形式(已完成)~~

~~2.添加邮件通知功能(失败github会自己发邮件)~~

~~3.这种自动生成的api应该可以通过别的方式识别，再想办法(使用打码平台验证码识别接口)~~
