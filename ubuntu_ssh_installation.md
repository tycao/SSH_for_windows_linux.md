1.安装
Ubuntu缺省安装了openssh-client,所以在这里就不安装了，如果你的系统没有安装的话，再用apt-get安装上即可。
安装ssh-server
sudo apt-get install openssh-server
安装ssh-client
sudo apt-get install openssh-client
2.确认sshserver是否安装好
ps -e | grep sshd
  450 ?        00:00:00 sshd
如果看到sshd那说明ssh-server已经启动了。 
如果只有ssh-agent说明ssh-server还没有启动，需要执行命令启动ssh服务：
/etc/init.d/ssh start；
注：在ubuntu-12.04-server-i386.iso安装中只显示sshd这一项：
3.扩展配置
SSH默认服务端口为22，用户可以自已定义成其他端口，如222，需要修改的配置文件为：
/etc/ssh/sshd_config
把里面的Port参数修改成222即可
然后重启SSH服务： 
sudo/etc/init.d/ssh restart
