

Powershell基础入门及常见用法   
https://www.toutiao.com/i6828797086176117262/?tt_from=weixin&utm_campaign=client_share&wxshare_count=1&timestamp=1590005811&app=news_article&utm_source=weixin&utm_medium=toutiao_ios&req_id=20200521041651010130036163322503C7&group_id=6828797086176117262

```
check version   
psversiontable

linux：ls    
cmd：dir   

ls | format-table name, mode

ls | format-table name, mode > demo.txt
type demo.txt
“type demo.txt”打印文件内容

查看端口信息
netstat -ano

查看网络配置信息
ipconfig

打印路由信息

route print

自定义文件路径，打开应用程序

start notepad
notepad

系统变量

$env:path

获取其用法的命令如下，简称gcm。

get-help get-command

获取进程信息

get-process

获取当前会话的别名

get-alias

获取当前时间

get-date

获取所有命令get-command可以用别名gcm替代。

get-command
gcm

获取当前目录的所有文件信息get-childitem，可以用ls、dir两个命令达到同样的效果。

get-childitem
ls
dir

get-help get-childitem


```

