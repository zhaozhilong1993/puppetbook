# 让Puppet运行在httpd之下

puppet使用SSL\(https\)协议来进行通讯，默认情况下，puppet server端使用基于Ruby的WEBRick HTTP服务器。由于WEBRick HTTP服务器在处理agent端的性能方面并不是很强劲，因此官方推介，在正式的生产环境中，把puppet-master运行在Apache的代理之下,使用Apache或者其他强劲的web服务器来处理客户的https请求。

```
yum install -y httpd httpd-devel mod_ssl \
ruby-devel rubygems gcc-c++ curl-devel zlib-devel make automake  openssl-devel
```

切换 ruby的默认源

```
[root@puppet-master ~]# gem source ls
*** CURRENT SOURCES ***

https://rubygems.org/

[root@puppet-master ~]# gem source -d https://rubygems.org/
[root@puppet-master ~]# gem source -a https://gems.ruby-china.org
```



```
# gem install json
# gem install rack -v=1.2.5
# gem install passenger -v=4.0.5
```


