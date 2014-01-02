### 在Ubuntu上SublimeText无法输入中文的解决方法
## 下载sublime-imfix.c
## 安装c\C++编译环境和gtk libgtk2.0-dev
* sudo apt-get install build-essential
* sudo apt-get install libgtk2.0-dev
## 编译共享库
* gcc -shared -o libsublime-imfix.so sublime_imfix.c  `pkg-config --libs --cflags gtk+-2.0` -fPIC
## 启动 Sublime Text 2
* LD_PRELOAD=./libsublime-imfix.so sublime_text

### 博客：http://my.oschina.net/zlLeaf/blog/185428
### 来源：http://my.oschina.net/wugaoxing/blog/121281
