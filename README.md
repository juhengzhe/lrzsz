# lrzsz
lrzsz是一款在linux里可代替ftp上传和下载的程序。
本文介绍如何在iterm2里添加lrzsz支持
# 1.linux服务器安装lrzsz
<code>yum install lrzsz</code>
# 2.mac安装iterm2
# 3.mac安装lrzsz
<code>brew install lrzsz</code>
# 4.下载脚本
<code>
cd /usr/local/bin
sudo wget https://raw.github.com/juhengzhe/lrzsz/master/iterm2-send-zmodem.sh
sudo wget https://raw.github.com/juhengzhe/lrzszmaster/iterm2-recv-zmodem.sh
sudo chmod 777 /usr/local/bin/iterm2-*
</code>
# 5.配置iterm2
preferences → profiles，选择某个profile，如Default，之后选择advanced → triggers，添加编辑添加如下triggers
triggers1：
Regular expression: /*/*B0100
Action: Run Silent Coprocess
Parameters:/usr/local/bin/iterm2-send-zmodem.sh
 
triggers2：
Regular expression: /*/*B00000000000000
Action: Run Silent Coprocess
Parameters:/usr/local/bin/iterm2-recv-zmodem.sh

