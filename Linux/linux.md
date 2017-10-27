## 查看并杀死进程
```
// 比较简单直接的方法
netstat -ano|findstr '8085' // 查看8085端口的占用情况，查询的结果中会 提示此端口对应的 PID（如112536）
tskill '112536'  // 可直接杀死112536进程

// 也可
netstat -ano //查看所有进程
netstat -ano|findstr '8085'  // 查看8085端口的占用情况，查询的结果中会 提示此端口对应的 PID（如112536）
tasklist // 查看所有运行的进程和对应程序名
tasklist findstr '112536' //查看指定PID(如112536对应的应用程序),查询结果如： node.exe   112536 Console   12   66,004 K
taskkill /f /t /im node.exe // 按im映射名杀死进程， 也可： tskill /f /pid 112536 (按pid杀死进程)


```
## 说明
**大小写均可识别**
```
taskkill /f /t /im node.exe 
taskkill /?来获取更多更多有关taskkill的信息。
 /S    system           指定要连接的远程系统。
 /U    [domain\]user    指定应该在哪个用户上下文执行这个命令。
 /P    [password]       为提供的用户上下文指定密码。如果忽略，提示输入。
 /FI   filter           应用筛选器以选择一组任务。允许使用 "*"。例如，映像名称 eq acme*
 /PID  processid        指定要终止的进程的 PID。使用 TaskList 取得 PID。
 /IM   imagename        指定要终止的进程的映像名称。通配符 '*'可用来指定所有任务或映像名称。
 /T                     终止指定的进程和由它启用的子进程。
 /F                     指定强制终止进程。
 /?                     显示帮助消息。
 
```
