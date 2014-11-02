在Ubuntu上SublimeText无法输入中文的解决方法
===

0. 下载sublime-imfix.c  
假设下载到了 home（～）目录下

0. 安装c\C++编译环境和gtk libgtk2.0-dev  
终端下输入以下命令：  
	`sudo apt-get install build-essential  libgtk2.0-dev`

0. 编译共享库  
终端下输入以下命令：  
	``gcc -shared -o libsublime-imfix.so sublime_imfix.c  `pkg-config --libs --cflags gtk+-2.0` -fPIC``

	> 该命令需要在 home 目录下执行， 即 **sublime-imfix.c** 所在目录

0. 将编译好的库移到 sublime 的安装目录  
终端下输入以下命令：  
	`mv libsublime-imfix.so $SUBLIME_HOME/`

	> + 该命令需要在 home 目录下执行， 即 **libsublime-imfix.so** 所在目录
	> + **$SUBLIME_HOME**，指Sublime的安装（所在）目录

0. 启动 Sublime Text 2  
终端下输入以下命令：  
	`LD_PRELOAD=./libsublime-imfix.so ./sublime_text`

	>  该命令需要在 sublime 的安装目录下执行  
	> 否则，需要将命令中的两个文件换成绝对路径

#### 博客：http://my.oschina.net/zlLeaf/blog/185428
#### 来源：http://my.oschina.net/wugaoxing/blog/121281
#### 博客：http://www.cnblogs.com/memory4young/p/could-not-input-chinese-in-sublime-on-ubuntu.html
