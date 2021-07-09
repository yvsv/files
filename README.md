1. SynFlood 攻击
借助netsniff-ng套件中的trafgen工具，其可伪造源ip发起DDoS攻击

trafgen是一款高速的，多线程数据包生成器，官方测试显示其速度可达到12Mpps，自己在Intel(R) Xeon(R) CPU E5-2620 v3 @ 2.40GHz下测得的发包速率有500Mbit/s多。通过对比其他开源程序，本工具的发包性能是自己测试中性能表现最高的。
synflood.trafgen是对应的配置文件模版，修改文件里的源／目的MAC地址以及源／目的IP后，命令行直接运行trafgen --cpp --dev eth0 --conf synflood.trafgen --cpu 2 --verbose即可发起synflood攻击
通过添加trafgen命令行参数--gap修改发包的速率，具体请man trafgen
对应工具可直接通过在线源进行安装，CentOS下yum install netsniff-ng即可安装整个套件，其中包含trafgen等工具。（预先可能需安装fedora源，yum install epel-release.noarch -y）
2. AckFlood 攻击
同SynFlood类似

ackflood.trafgen是对应的配置文件模版，修改文件里的源／目的MAC地址以及源／目的IP后，命令行直接运行trafgen --cpp --dev eth0 --conf ackflood.trafgen --cpu 2 --verbose即可发起ackflood攻击
