# register_domain

批量扫描域名是否被注册

## 检查原理

通过 api 接口 http://panda.www.net.cn/cgi-bin/check.cgi?area_domain= 查询域名状态


（注意：不要盯着这一个接口坑，小心干翻别人的接口，小心自己被封IP）


浏览器访问 http://panda.www.net.cn/cgi-bin/check.cgi?area_domain=itdhz.com ，得到下面内容

    <?xml version="1.0" encoding="gb2312"?>
    <property>
    <returncode>200</returncode>
    <key>itdhz.com</key>
    <original>211 : Domain exists</original>
    </property>

返回内容中，状态为 211 表示域名已经被注册， 状态为 210 表示域名可以注册。

## 脚本运行

    [root@itdhz ~]# python register_domain.py &
    
后台运行程序，然后当前目录会生成 domain_enable.txt 文件，文件中记录可以注册的5位字母的域名。

    [root@itdhz ~]# tail -f domain_enable.txt
    bhuuv.com
    bhuuw.com
    bhuux.com
    bhuuy.com
    bhuuz.com
    bhuvb.com
    bhuvc.com
    bhuvd.com
    bhuvf.com
