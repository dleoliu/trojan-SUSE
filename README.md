# trojan-SUSE

专为 **SUSE Linux Enterprise（SLE）** 及 **openSUSE** 优化过的trojan多用户管理部署程序。

基于[Jrohy/trojan](https://github.com/Jrohy/trojan)。详细参见上游项目或 `upstream` 分支。

Trojan是一种安全且现代化的虚拟专用网络协议，详细参见[Trojan](https://github.com/trojan-gfw/trojan)。

## SUSE优化

- Zypper支持
- 施工中：使用Zypper的自动vnstat安装与配置
- 施工中：使用Zypper的自动Docker安装与配置

※当前安装脚本依旧可供Debian及RHEL系Linux使用。今后停止对SUSE系以外Linux支持的可能。

## 已测试SUSE

### SUSE Linux Enterprise Server(SLES)

- SLES 15 ~ SLES 15 SP4
- SLES 12 SP5

### openSUSE

- openSUSE Leap 15.2（将结束支持）
- openSUSE Leap 15.3 / 15.4
- openSUSE Tumbleweed

## 功能
- 在线web页面和命令行两种方式管理trojan多用户
  - 启动 / 停止 / 重启 trojan 服务端
  - 在线实时查看trojan日志
  - 在线trojan和trojan-go随时切换
  - 支持trojan://分享链接和二维码分享
  - 支持转化为clash订阅地址并导入到[clash_for_windows](https://github.com/Fndroid/clash_for_windows_pkg/releases)
- 支持流量统计和流量限制
- 命令行模式管理, 支持命令补全
- 集成acme.sh证书申请
- 生成客户端配置文件
- 限制用户使用期限

## 安装方式
**trojan使用请提前准备好服务器可用的域名。推荐使用SLES或openSUSE Leap。**

### 安装/更新
```
git clone https://github.com/optimusleobear/trojan-SUSE.git
cd trojan-SUSE/
source install.sh
```
安装完后输入'trojan'可进入管理程序。

浏览器访问域名可在线web页面管理trojan用户。

前端页面源码地址: [trojan-web](https://github.com/Jrohy/trojan-web)。

### 卸载
```
cd trojan-SUSE/
source install.sh --remove
```

## 运行截图
![avatar](asset/1.png)
![avatar](asset/2.png)

## 命令行
```
Usage:
  trojan [flags]
  trojan [command]

Available Commands:
  add           添加用户
  clean         清空指定用户流量
  completion    自动命令补全(支持bash和zsh)
  del           删除用户
  help          Help about any command
  info          用户信息列表
  log           查看trojan日志
  port          修改trojan端口
  restart       重启trojan
  start         启动trojan
  status        查看trojan状态
  stop          停止trojan
  tls           证书安装
  update        更新trojan
  updateWeb     更新trojan管理程序
  version       显示版本号
  import [path] 导入sql文件
  export [path] 导出sql文件
  web           以web方式启动

Flags:
  -h, --help   help for trojan
```
