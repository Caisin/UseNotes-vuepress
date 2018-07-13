

## [frps一键安装脚本地址](https://github.com/clangcn/onekey-install-shell/tree/master/frps)

```shell
# 安装
wget --no-check-certificate https://raw.githubusercontent.com/clangcn/onekey-install-shell/master/frps/install-frps.sh -O ./install-frps.sh && chmod 700 ./install-frps.sh && ./install-frps.sh install
# 升级
bash install-frps.sh update
#卸载
bash install-frps.sh uninstall
```


```
Loading network version for frps, please wait...
frps Latest release file frp_0.8.1_linux_amd64.tar.gz    #此步骤会自动获取frp最新版本，自动操作，无需理会
Loading You Server IP, please wait...
You Server IP:12.12.12.12                                           #自动获取你服务器的IP地址
Please input your server setting:

Please input frps bind_port [1-65535](Default Server Port: 5443):      #输入frp提供服务的端口，用于服务器端和客户端通信
Please input frps dashboard_port [1-65535](Default dashboard_port: 6443): #输入frp的控制台服务端口，用于查看frp工作状态
Please input frps vhost_http_port [1-65535](Default vhost_http_port: 80):  #输入frp进行http穿透的http服务端口
Please input frps vhost_https_port [1-65535](Default vhost_https_port: 443): #输入frp进行https穿透的https服务端口
Please input privilege_token (Default: WEWLRgwRjIJVPx2kuqzkGnvuftPLQniq): #输入frp服务器和客户端通信的密码，默认是随机生成的
Please input frps max_pool_count [1-200](Default max_pool_count: 50):     #设置每个代理可以创建的连接池上限，默认50

##### Please select log_level #####
1: info
2: warn
3: error
4: debug
#####################################################
Enter your choice (1, 2, 3, 4 or exit. default [1]):        #设置日志等级，4个选项，默认是info

Please input frps log_max_days [1-30]
(Default log_max_days: 3 day):            #设置日志保留天数，范围是1到30天，默认保留3天。

##### Please select log_file #####
1: enable
2: disable
#####################################################
Enter your choice (1, 2 or exit. default [1]):      #设置是否开启日志记录，默认开启，开启后日志等级及保留天数生效，否则等级和保留天数无效

```

## 管理命令
```shell
/etc/init.d/frps start
/etc/init.d/frps stop
/etc/init.d/frps restart
/etc/init.d/frps status
/etc/init.d/frps config
/etc/init.d/frps version
```

## [客户端下载](https://github.com/fatedier/frp/releases)

## [客户端配置](https://github.com/fatedier/frp/blob/master/README_zh.md#%E9%80%9A%E8%BF%87%E8%87%AA%E5%AE%9A%E4%B9%89%E5%9F%9F%E5%90%8D%E8%AE%BF%E9%97%AE%E9%83%A8%E7%BD%B2%E4%BA%8E%E5%86%85%E7%BD%91%E7%9A%84-web-%E6%9C%8D%E5%8A%A1)