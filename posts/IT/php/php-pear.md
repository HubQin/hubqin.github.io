## PHP pear，mdb2，mysql/mysqli driver install


Under CentOS7
# install pear：
```
$ wget http://pear.php.net/go-pear.phar
$ php go-pear.phar
```   
不知什么原因，安装完之后，运行pear，提示找不到命令，在/usr/bin查看，文件名字是pear_old,于是将名字改为pear，运行成功。
# install MDB2
`pear install mdb2`
## install mysql driver，mysqli driver
安装过程中，会提示有哪些可选的feature以及如何安装这些feature：
`pear install pear/MDB2#featurename`
例如我要安装mysql driver，mysqli driver，分别运行：
`pear install pear/MDB2#mysql`
`pear install pear/MDB2#mysqli`
安装完成后，搜索MDB2.php文件，查看安装目录，是在/usr/share/pear.也可以运行：
`pear config-get php_dir` 查看安装目录。
# Verifying the include path
我自己系统上的php.ini路径是：`/etc/php.ini`,运行：
 `php -c /etc/php.ini -r 'echo get_include_path()."\n";'` 查看include path，我自己运行的输出结果：
 `.:/usr/share/pear:/usr/share/php`
 PEAR's php_dir should be in the include path. If not, add it in your system's php.ini.
 [reference](http://pear.php.net/manual/en/installation.checking.php) 
# test
PHP and Mysql Web Developemt 的文件 search_generic.html，results_generic.php 运行成功。



