#1.Linux目录结构

<img src="C:\Users\王多鱼\AppData\Roaming\Typora\typora-user-images\image-20220312161414143.png" alt="image-20220312161414143" style="zoom:150%;" />  

1）/bin （/usr/bin、/usr/local/bin) 是binary的缩写，存放常用的命令

2）/sbin  （/usr/sbin、/usr/local/sbin）super user ，存放系统管理员使用的系统管理程序

3）/home 存放普通用户的主目录，在Linux中每个用户都有自己的目录

4） /root 系统管理员的主目录

5）/lib 系统开机所需的动态链接共享库，类似Windows的DLL文件，应用程序需要这些共享库

6）/lost+found 系统非法关机存放的文件

<img src="C:\Users\王多鱼\AppData\Roaming\Typora\typora-user-images\image-20220312162335807.png" alt="image-20220312162335807"  />

16）/mnt  挂载外部存储

<img src="C:\Users\王多鱼\AppData\Roaming\Typora\typora-user-images\image-20220312162600464.png" alt="image-20220312162600464" style="zoom: 150%;" />

# 2.vi和vim编辑器

用vim打开文件进入==默认模式==

按i进入==插入模式==

输入esc再输入：进入==命令行模式==

![image-20220312163216308](C:\Users\王多鱼\AppData\Roaming\Typora\typora-user-images\image-20220312163216308.png)

<img src="C:\Users\王多鱼\AppData\Roaming\Typora\typora-user-images\image-20220312163229983.png" alt="image-20220312163229983" style="zoom:150%;" />

![image-20220312163331337](C:\Users\王多鱼\AppData\Roaming\Typora\typora-user-images\image-20220312163331337.png)

# 3.关机、重启和用户登录注销

![image-20220312163504662](C:\Users\王多鱼\AppData\Roaming\Typora\typora-user-images\image-20220312163504662.png)

==重启或关闭系统，首先要运行sync命令，把内存中的数据写到磁盘==

普通用户登录后用==su - 用户名==来切换root身份

==logout==注销用户（在图形运行级别无效，级别三有效）

# 4.用户管理

添加用户： ==useradd   用户名==

==useradd -d 指定目录 用户名==  给新用户指定家目录

指定或修改密码： ==passwd 用户名==

==pwd==显示当前用户所在目录

删除用户 但保留家目录==userdel  用户名==

删除用户及主目录==userdel -r 用户名==

-----

查询用户  ==id 用户名==

切换用户名  ==su - root==（切换用户名）

返回原来用户 ==exit/logout==

查看当前用户 ： ==whoami/who am i==

--------

用户组： ==groupadd 组名== 

 ==groupdel 组名==

==useradd -g 用户组  用户名==

修改用户组： ==usermod -g 用户组  用户名==

--------

用户和组相关文件

![image-20220312170725939](C:\Users\王多鱼\AppData\Roaming\Typora\typora-user-images\image-20220312170725939.png)

![image-20220312170747741](C:\Users\王多鱼\AppData\Roaming\Typora\typora-user-images\image-20220312170747741.png)

# 5.Linux实用指令

![image-20220312170847451](C:\Users\王多鱼\AppData\Roaming\Typora\typora-user-images\image-20220312170847451.png)

![image-20220312171023333](C:\Users\王多鱼\AppData\Roaming\Typora\typora-user-images\image-20220312171023333.png)

------------------

找回root密码：在服务器实体位置进行，输入一系列指令

帮助指令： ==man  [命令或配置文件]==  eg：man ls

linux下隐藏文件以.开头，可以组合使用选项   ls -al  ls -al/root   

 help指令： ==help  命令==   （获得shell内置命令的帮助信息）

-------------------

1. ==pwd==（显示当前工作目录的绝对路径）

2. ==ls==    -a（显示所有文件，包括隐藏文件）-l （以列表显示信息）

3. ==cd==    cd  ~ 返回当前用户的家目录   cd..  回到上一级目录

4. ==mkdir==     -p（创建多级目录） 

5. ==rmdir==   只能删除空目录   非空（rm -rf）

6. ==touch==    创建空文件如hello.txt

7. ==cp==  拷贝到指定目录   ==cp[选项]源地址==   -r递归复制整个文件夹

    强制覆盖不提示的方法：\cp , \cp -r /home/bbb /opt

8. ==rm==   -r ：递归删除整个文件夹   -f ： 强制删除不提示

9. ==mv==   移动文件与目录或重命名  mv oldNameFile newNameFile (功能描述:重命名)

    mv /temp/movefile /targetFolder (功能描述:移动文件)                                     		

10. ==cat==   查看文件内容     -n ：显示行号  cat 只能浏览文件,而不能修改文件,为了浏览方便,一般会带上==管道命令 | more==        cat -n /etc/profile | more [进行交互]

11. ==more== 指令是一个基于 VI 编辑器的文本过滤器,它以全屏幕的方式按页显示文本文件的内容.more 指令中内置了若干快捷键(交互的指令)    ==more 要查看的文件==   <img src="C:\Users\王多鱼\AppData\Roaming\Typora\typora-user-images\image-20220312192955470.png" alt="image-20220312192955470" style="zoom:80%;" />

12. ==less==   功能与 more 指令类似,但是比 more 指令更加强大,支持各种显示终端.less 指令在显示文件内容时,并不是一次将整个文件加载之后才显示,而是根据显示需要加载内容,对于显示大型文件具有 较高的效率.==less 要查看的文件== 

      ![image-20220312193900551](C:\Users\王多鱼\AppData\Roaming\Typora\typora-user-images\image-20220312193900551.png)

13. ==echo==   输出内容到控制台  echo [选项] [输出内容]案例：使用echo指令输出环境变量，比如输出$PATH   $HOSTNAME， echo$HOSTNAME   案例：使用echo指令输出你好，世界！

14. ==head==   用于显示文件的开头部分内容,默认情况下 head 指令显示文件的前 10 行内容head -n 5 文件名 (查看文件头 5 行内容,5 可以是任意行数)

15. ==tail==   输出文件中尾部的内容,默认情况下 tail 指令显示文件的前 10 行内容.  1) tail 文件 (查看文件尾 10 行内容) 2) tail -n 5 文件 (查看文件尾 5 行内容,5 可以是任意行数) 3) tail -f 文件 (实时追踪该文档的所有更新)

16. ==>输出重定向和   >> 追加==   1) ls -l >文件 (列表的内容写入文件 a.txt 中(覆盖写)) 2) ls -al >>文件 (列表的内容追加到文件 aa.txt 的末尾) 3) cat 文件 1 > 文件 2 (将文件 1 的内容覆盖到文件 2)  4) echo "内容">> 文件 (追加)  ls -l /home > /home/info.txt ==如果 info.txt 没有,则会创建== 

17. ==ln==  软链接也称为符号链接,类似于 windows 里的快捷方式,主要存放了链接其他文件的路径 ==ln -s [原文件或目录] [软链接名] (给原文件创建一个软链接)==  案例 1: 在/home 目录下创建一个软连接 myroot,连接到 /root 目录 ln -s /root /home/myroot 案例 2: 删除软连接 myroot rm /home/myroot使用pwd查看目录时,仍看到的是软链接所在目录.

18. ==history==  查看已经执行过历史命令,也可以执行历史指令  案例 1: 显示所有的历史命令 history 案例 2: 显示最近使用过的 10 个指令 history 10 案例 3：执行历史编号为 5 的指令 ==!5==  

    --------------------------

    **时间日期类** ：

    1. ==date==   显示当前时间    ==date +%Y== 显示当前年份     ==date +%m==  显示当前月份    ==date +%d== 显示当前是哪一天    ==date "+%Y-%m-%d %H:%M:%S"==    显示年月日时分秒
    
       案例 1: 显示当前时间信息 ==date==      案例 2: 显示当前时间年月日 ==date "+%Y-%m-%d"==  案例3：显示当前时间年月日时分秒日期   ==“+%Y-%M-%d%H：%M：%S”==
    
     2.date 指令-设置日期    ==date -s==  字符串时间 案例1：设置系统当前时间，比如设置成2020-11-03 20：02：10      date -s  “2020-11-03 20：02：10”

​		3. cal 指令 查看日历指令==cal==  基本语法 ==cal [选项]== =不加选项,显示本月日历   应用实例 案例 1: 显示当前日历 ==cal==   案例 2: 显示 2020 年日历 : ==cal 2020==

**搜索查找类**  ：

1.==find指令==   find 指令将从指定目录向下递归地遍历其各个子目录,将满足条件的文件或者目录显示在终端.

基本语法 find [搜索范围] [选项]![image-20220326105637830](C:\Users\王多鱼\AppData\Roaming\Typora\typora-user-images\image-20220326105637830.png)

案例1：按文件名:根据名称查找/home 目录下的 hello.txt 文件  ==find /home -name hello.txt== 案例 2:按拥有者:查找/opt 目录下,用户名称为 nobody 的文件 ==find /opt -user nobody== 案例 3:查找整个 linux 系统下大于 200M 的文件(==+n 大于 -n 小于 n 等于==, 单位有 k,M,G)    find / -size +200M

2。==locate== 指令    locate 指令可以快速定位文件路径，locate 指令利用事先建立的系统中所有文件名称及路径的 ==locate 数据库==实现快速定位给定的文件。locate 指令无需遍历整个文件系统,查询速度较快.为了保证查询结果的准确度,管理员必须定期更新 locate 时刻 。基本语法 locate 搜索文件   特别说明 由于 locate 指令基于数据库进行查询,所以第一次运行前,必须使用 ==updatedb== 指令创建 locate 数据库. 

 案例 1: 请使用 locate 指令快速定位 hello.txt 文件所在目录     ==which== 指令,可以查看某个指令在哪个目录下,比如 ls 指令在哪个目录==which ls==

3.==grep 指令和 管道符号 |==  grep 过滤查找 , 管道符“|”表示将前一个命令的处理结果输出传递给后面的命令处理.

![image-20220326110406878](C:\Users\王多鱼\AppData\Roaming\Typora\typora-user-images\image-20220326110406878.png)

案例1：请在hello.txt文件中查找“yes”所在行，并且显示行号  写法1：==cat /home/hello.txt| grep==  “yes”  写法2：grep  -n  “yes”  /home/hello.txt  

**压缩和解压类**

1     ==gzip/gunzip==     gzip 用于压缩文件, gunzip 用于解压     基本语法  gzip  文件 (压缩文件,只能将文件压缩为*.gz 文件)    gunzip 文件.gz (解压缩文件命令) 应用实例  

案例 1: gzip 压缩, 将 /home 下的 hello.txt 文件进行压缩  ==gzip/home/hello.txt==   案例2：gunzip压缩，将/home下的hello.txt.gz文件进行解压缩    ==gunzip /home/hello.txt.gz==   

2.==zip/unzip==      zip 用于压缩文件, unzip 用于解压,这个在项目打包发布中很有用     基本语法 zip [选项] XXX.zip 将要压缩的内容(功能描述：压缩文件和目录的命令)       unzip [选项] XXX.zip (功能描述：解压缩文件) 

zip 常用选项 -r：递归压缩,即压缩目录    unzip 的常用选项 -d<目录> ：指定解压后文件的存放目录 

 案例1：将/home下的所有文件/文件夹进行压缩成myhome.zip   ==zip  -r  myhome.zip  /home/==  将home目录及其包含的文件和子文件夹都压缩 案例2：将myhome.zip解压到/opt/tmp目录下  unzip -d /opt/tmp /home/myhome.zip     

3. ==tar== 指令   tar指令是打包指令,最后打包后的文件是==.tar.gz==的文件.  tar [选项] XXX.tar.gz  打包的内容 (功能描述：打包目录,压缩后的文件格式.tar.gz)![image-20220326111847305](C:\Users\王多鱼\AppData\Roaming\Typora\typora-user-images\image-20220326111847305.png)

案例1：压缩多个文件，将/home/pig.txt和/home/cat.txt压缩成pc.tar.gz   ==tar -zcvf   /home/pig.txt  /home/cat.txt==  案例2：将/home的文件夹压缩成myhome.tar.gz   tar -zcvf myhome.tar.gz  /home/  案例3：将pc.tar.gz解压到当前目录  tar -zxvf pc.tar.gz   案例4：将myhome.tar.gz解压到/opt/tmp2目录下==tar-zxvf  /home/myhome.tar.gz   -C/opt/tmp2==   

# 6.组管理和权限管理#

linux 中的每个用户必须属于一个组,不能独立于组外.在 linux 中每个文件 有所有者,所在组,其它组的概念.谁创建了该文件,就自然的成为该文件的所有者.

1.查看文件的所有者 指令：==ls –ahl==  

![image-20220326112614723](C:\Users\王多鱼\AppData\Roaming\Typora\typora-user-images\image-20220326112614723.png)

2.修改文件所有者   指令：==chown 用户名 文件名== 应用案例 要求：使用 root 创建一个文件 apple.txt ,然后将其所有者修改成 tom    ==chown tom apple.txt==   

3.组的创建   ==groupadd  组名==     创建一个组monster ==group monster==   创建一个用户fox，并放入到monster组中    ==useradd -g  monster fox==

4.文件/目录所在组   当某个用户创建了一个文件后,这个文件的所在组就是该用户所在的组  

查看文件/目录所在组 基本指令 ==ls –ahl==    使用 fox 来创建一个文件,看看该文件属于哪个组?

![image-20220326113107076](C:\Users\王多鱼\AppData\Roaming\Typora\typora-user-images\image-20220326113107076.png)

修改文件/目录所在的组  基本指令 ==chgrp 组名 文件名==   应用实例 使用 root 用户创建文件 orange.txt ,看看当前这个文件属于哪个组,然后将这个文件所在组修改到 fruit 组 1. groupadd fruit 2. touch orange.txt 3. 看看当前这个文件属于哪个组 -> root 组 4. ==chgrp fruit orange.txt==

5.其它组 除文件的所有者和所在组的用户外,系统的其它用户都是文件的其它组

6.改变用户所在组 在添加用户时,可以指定将该用户添加到哪个组中,同样的用 root 的管理权限可以改变某个用户所在的组. 

 改变用户所在组 ==usermod –g 新组名 用户名==  ==usermod –d 目录名 用户名==   改变该用户登陆的初始目录.  特别说明：==用户需要有进入到新目录的权限==    应用实例 将 zwj 这个用户从原来所在组,修改到 wudang 组 usermod -g wudang zwj

7 .权限的基本介绍  ls -l  显示的内容如下： -rwxrw-r-- 1 root root 1213 Feb 2 09:39 abc

 0-9 位说明 第 0 位确定文件类型(d, - , l , c , b) l 是链接,相当于 windows 的快捷方式 d 是目录,相当于 windows 的文件夹 c 是字符设备文件,鼠标,键盘  b 是块设备,比如硬盘 第 1-3 位确定所有者(该文件的所有者)拥有该文件的权限.   第 4-6 位确定所属组(同用户组的)拥有该文件的权限  第 7-9 位确定其他用户拥有该文件的权限 

8.rwx 作用到文件    1) [ r ]代表可读(read): 可以读取,查看 2) [ w ]代表可写(write): 可以修改,但是不代表可以删除该文件,==删除一个文件的前提条件是对该文件所在的目录有写权限==,才能删除该文件. 3) [ x ]代表可执行(execute):可以被执行

rwx 作用到目录 1) [ r ]代表可读(read): 可以读取,ls 查看目录内容 2) [ w ]代表可写(write): 可以修改, 对目录内创建+删除+重命名目录   3) [ x ]代表可执行(execute):可以进入该目录

9.文件及目录权限实际案例    

ls -l 中显示的内容如下： -rwxrw-r-- ==1== root root 1213 Feb 2 09:39 abc  第一组 rwx : 文件拥有者的权限是读,写和执行 第二组 rw- : 与文件拥有者同一组的用户的权限是读,写但不能执行 第三组 r-- : 不与文件拥有者同组的其他用户的权限是读不能写和执行  可用数字表示为: r=4,w=2,x=1 因此 rwx=4+2+1=7 , 数字可以进行组合 

其它说明 ==1== 文件：硬连接数 / 目录：子目录数 root 用户 root 组 1213 文件大小(字节),如果是文件夹,显示 4096 字节  Feb 2 09:39 最后修改日期   abc 文件名

10.  修改权限 ==chmod==   通过 chmod 指令,可以修改文件或者目录的权限. 

    第一种方式：+ ,-,= 变更权限  u:所有者 g:所有组 o:其他人 a:所有人(u,g,o 的总和)

    1) chmod u=rwx,g=rx,o=x 文件/目录名 2) chmod o+w 文件/目录名 3) chmod a-x 文件/目录名  案例 1) 给 abc 文件 的所有者读写执行的权限,给所在组读执行权限,给其它组读执行权限. chmod u=rwx,g=rx,o=rx abc 2) 给 abc 文件的所有者除去执行的权限,增加组写的权限 chmod u-x,g+w abc 3) 给 abc 文件的所有用户添加读的权限 chmod a+r abc 

第二种方式：通过数字变更权限 r=4 w=2 x=1 rwx=4+2+1=7 chmod u=rwx,g=rx,o=x 文件目录名 相当于 ==chmod 751 文件/目录名==   要求：将 /home/abc.txt 文件的权限修改成 rwxr-xr-x, 使用给数字的方式实现：chmod  755 /home/abc.txt

11.  修改文件所有者==chown==      ==chown newowner== 文件/目录 改变所有者 

    ==chown newowner:newgroup 文件/目录== 改变所有者和所在组 ==-R 如果是目录== 则使其下所有子文件或目录递归生效  

    案例演示 1) 请将 /home/abc.txt 文件的所有者修改成 tom ==chown tom /home/abc.txt== 2) 请将 /home/test 目录下所有的文件和目录的所有者都修改成 tom ==chown -R tom /home/test==

12.修改文件/目录所在组==chgrp==    chgrp新组文件/目录 

案例演示请将/home/abc.txt文件的所在组修改成shaolin组   groupadd shaolin  chgrp  shaolin   /home/abc.txt

请将/home/test目录下所有的文件和目录的所在组都修改成shaolin    ==chgrp -R shaolin /home/test==

13最佳实践-警察和土匪游戏police,bandit 

jack，jerry：警察  xh，xq：土匪

1)创建组群添加警察==groupadd police  groupadd bandit==；

2)创建用户 ==useradd -g police jack useradd -g police jerry==  

3)jack创建一个文件，自己可以读写，本组人可以读，其它组没人任何权限

首先jack登录;==vim jack.txt     ; chmod 640 jack.txt==

4)jack修改该文件，让其它组人可以读，本组人可以读写==chmod o=r,g=wr jack.txt

5)xh投靠警察，看看是否可以读写。==usermod -g police xh==

6)看看xh 是否可以读写,xq 是否可以.==如果要对目录内的文件进行操作,需要要有对该目录的 相应权限==

# 7.定时任务调度

1.==crond== 任务调度 ==crontab== 进行定时任务的设置  任务调度是指系统在某个时间执行的特定的命令或程序. 任务调度分类：1.系统工作：有些重要的工作必须周而复始地执行.如病毒扫描等 个别用户工作：个别用户可能希望执行某些程序,比如对 mysql 数据库的备份.

![image-20220326145715769](C:\Users\王多鱼\AppData\Roaming\Typora\typora-user-images\image-20220326145715769.png)

==crontab[选项]==![image-20220326145823130](C:\Users\王多鱼\AppData\Roaming\Typora\typora-user-images\image-20220326145823130.png)

设置任务调度文件：/etc/crontab 设置个人任务调度：执行 crontab –e 命令. 接着输入任务到调度文件 如： */1 * * * * ls –l  /etc/ > /tmp/to.txt 意思是每小时的每分钟执行 ls –l /etc/ > /tmp/to.txt 命令

![image-20220326150233365](C:\Users\王多鱼\AppData\Roaming\Typora\typora-user-images\image-20220326150233365.png)

![image-20220326150350494](C:\Users\王多鱼\AppData\Roaming\Typora\typora-user-images\image-20220326150350494.png)

案例1：每隔1分钟，就将当前的日期信息，追加到 /tmp/mydate   */1 date>> /tmp/mydate*

案例2：每隔1分钟，将当前日期和日历都追加到/home/mycal文件中

步骤：1.vim/home/my.sh  写入内容  date >> /home/mycal 和cal >>/home/cal

(2)给my.sh增加执行权限，chmod u+x /home/my.sh

（3）crontab -e   增加 */1 /home/my.sh

案例3：每天凌晨2：00将数据库testdb，备份到文件中（1）crontab -e  （2）0 2 *** mysqldump -u root -proot testdb >/home/db.bak

 crond 相关指令 ==conrtab –r==：终止任务调度.  ==crontab –l==：列出当前有那些任务调度 ==service crond restart== [重启任务调度]

2.at 定时任务  at 命令是一次性定时计划任务  at的守护进程 atd 会以后台模式运行,检查作业队列来运行.   默认情况下,atd 守护进程每 60 秒检查作业队列,有作业时,会检查作业运行时间,如果时间与当前时间匹配,则 运行此作业. at命令是一次性定时计划任务,执行完一个任务后不再执行此任务了,在使用 at 命令的时候,一定要保证 atd进程的启动 , 可以使用相关指令来查看 ps -ef | grep atd 可以检测 atd 是否在运行

at 命令格式  at [选项] [时间]      Ctrl + D 结束 at 命令的输入, 输出两次

![image-20220326152957691](C:\Users\王多鱼\AppData\Roaming\Typora\typora-user-images\image-20220326152957691.png)

at 指定时间的方法： 1) 接受在当天的h:m(小时:分钟)式的时间指定.假如该时间已过去,那么就放在第二天执行. 例如：04:00 2) 使用midnight(深夜),noon(中午),teatime(一般是下午 4 点)  采用 12 小时计时制,即在时间后面加上 AM或PM来说明是上午还是下午. 例如：12pm  指定命令执行的具体日期,指定格式为 month day(月 日)或 mm/dd/yy(月/日/年)或 dd.mm.yy(日.月.年),指 定的日期必须跟在指定时间的后面. 例如：04:00 2021-03-1 使用相对计时法.指定格式为：now + count time-units ,now 就是当前时间,time-units 是时间单位,这里能够是 minutes ,hours、days、weeks.count 是时间的数量,几天,几小时.例如：now+5minutes  6)直接使用today、tomorrow来指定完成命令的时间。

![image-20220326153740214](C:\Users\王多鱼\AppData\Roaming\Typora\typora-user-images\image-20220326153740214.png)

![image-20220326153843607](C:\Users\王多鱼\AppData\Roaming\Typora\typora-user-images\image-20220326153843607.png)

#8.Linux磁盘分区、挂载

Linux无论有几个分区,分给哪一目录使用,它归根结底就只有一个根目录,一个独立且唯一的文件结构 , Linux 中每个分区都是用来组成整个文件系统的一部分.  Linux 采用了一种叫“载入”的处理方法,它的整个文件系统中包含了一整套的文件和目录,且将一个分区和一个目录联系起来.这时要载入的一个分区将使它的存储空间在一个目录下获得.

![image-20220326154340753](C:\Users\王多鱼\AppData\Roaming\Typora\typora-user-images\image-20220326154340753.png)

Linux硬盘分 IDE硬盘和 SCSI 硬盘,目前基本上是 SCSI 硬盘   对于 IDE 硬盘,驱动器标识符为“hdx~”,其中“hd”表明分区所在设备的类型,这里是指 IDE 硬盘.“x”为盘号(a 为 基本盘,b 为基本从属盘,c 为辅助主盘,d 为辅助从属盘),“~”代表分区,前四个分区用数字 1 到 4 表示,它们是主分区或扩展分区,从 5 开始就是逻辑分区.例hda3 表示为第一个 IDE 硬盘上的第三个主分区或扩展分区,hdb2 表示为第二个 IDE 硬盘上的第二个主分区或扩展分区.

对于 SCSI 硬盘则标识为“sdx~”,SCSI 硬盘是用“sd”来表示分区所在设备的类型的,其余则和 IDE 硬盘的表示方法一样

查看所有设备挂载情况 命令 ：==lsblk 或者 lsblk -f==

![image-20220326155009952](C:\Users\王多鱼\AppData\Roaming\Typora\typora-user-images\image-20220326155009952.png)

以增加一块硬盘为例来熟悉下磁盘的相关指令和深入理解磁盘分区,挂载,卸载的概念。

如何增加一块硬盘  1) 虚拟机添加硬盘 2) 分区 3) 格式化 4) 挂载 5) 设置可以自动挂载 

分区命令 fdisk /dev/sdb 开始对/sdb 分区 m 显示命令列表 p 显示磁盘分区，同 fdisk –l  n 新增分区 d 删除分区 w 写入并退出 

 说明： 开始分区后输入 n,新增分区,然后选择 p ,分区类型为主分区.两次回车默认剩余全部空间.最后输入 w 写入分区并退出,若不保存退出输入 q.

![image-20220326155717081](C:\Users\王多鱼\AppData\Roaming\Typora\typora-user-images\image-20220326155717081.png)

格式化磁盘 分区命令: mkfs -t ext4 /dev/sdb1 其中 ext4 是分区类型 

 挂载: 将一个分区与一个目录联系起来, ==mount 设备名称 挂载目录== 例如：mount /dev/sdb1 /newdisk       ==umount 设备名称 或者 挂载目录==      umount  /dev/sdb1 或者umount / newdisk       ==用命令行挂载，重启后会失效==   ==永久挂载: 通过修改/etc/fstab 实现挂载 添加完成后 执行 mount –a 即刻生效==

磁盘情况查询 查询系统整体磁盘使用情况 ==df -h==  

![image-20220326160537110](C:\Users\王多鱼\AppData\Roaming\Typora\typora-user-images\image-20220326160537110.png)

查询指定目录的磁盘占用情况  ==du -h==   查询指定目录的磁盘占用情况,默认为当前目录 -s 指定目录占用大小汇总 -h 带计量单位 -a 含文件 --max-depth=1子目录深度   -c 列出明细的同时,增加汇总值  

应用实例 查询 /opt 目录的磁盘占用情况,深度为 1

![image-20220326161245486](C:\Users\王多鱼\AppData\Roaming\Typora\typora-user-images\image-20220326161245486.png)

磁盘情况-工作实用指令

1) 统计/opt 文件夹下文件的个数 ls -l /opt | grep "^-" | wc -l 

2)  统计/opt 文件夹下目录的个数 ls -l /opt | grep "^d" | wc -l

3)  统计/opt 文件夹下文件的个数,包括子文件夹里的ls-lR/opt|grep“^ -”|wc-l

4) 统计/选择文件夹下目录的个数，包括子文件夹里的    ls -lR /opt | grep “^d” |wc-l

5) 以树状显示目录结构树目录，注意，如果没有树，则使用yum install tree 安装

   ![image-20220326162950194](C:\Users\王多鱼\AppData\Roaming\Typora\typora-user-images\image-20220326162950194.png)

# 9.网络配置

![image-20220326163131475](C:\Users\王多鱼\AppData\Roaming\Typora\typora-user-images\image-20220326163131475.png)

查看网络 IP 和网关 

查看虚拟网络编辑器和修改 IP 地址

查看windows环境的VMnet8网络配置（ipconfig 指令）查看linux的网络配置ifconfig

ping 测试主机之间网络连通性 ==ping 目的主机== (功能描述：测试当前服务器是否可以连接目的主机) 13测试当前服务器是否可以连接百度 ping www.baidu.com 

1.linux 网络环境配置 

第一种方法(自动获取)： 说明：登陆通过界面来设置自动获取ip,特点：linux 启动后会自动获取 IP,缺点是每次自动获取的ip地址可能不一样。

第二种方法(指定 ip)   直接修改配置文件来指定 IP,并可以连接到外网     vi /etc/sysconfig/network-scripts/ifcfg-ens33 要求:将 ip 地址配置的静态的,比如:ip 地址为 192.168.200.130 

ifcfg-ens33文件说明   DEVICE=eth0 #接口名(设备,网卡)   HWADDR=00:0C:2x:6x:0x:xx #MAC 地址   TYPE=Ethernet #网络类型(通常是 Ethemet)  UUID=926a57ba-92c6-4231-bacb-f27e5e6a9f44 #随机 id       #系统启动的时候网络接口是否有效(yes/no) ONBOOT=yes

IP 的配置方法[none|static|bootp| dhcp]  (引导时不使用协议|静态分配 IP|BOOTP 协议|DHCP 协议) BOOTPROTO=static 

IP 地址 IPADDR=192.168.200.130  #网关GATEWAY=192.168.200.2

域名解析器DNS1=192.168.200.2  重启网络服务或重启系统生效 service network restart 、reboot

2.==设置主机名== 给 linux 系统设置主机名, 也可以根据需要修改主机==hostname== ： 查看主机名 修改文件在 /etc/hostname 指定 4) 修改后,重启生效 

==设置hosts映射== 如何通过主机名找到(比如 ping) 某个 linux 系统? 

 windows在C:\Windows\System32\drivers\etc\hosts  文件指定192.168.200.130  hspedu100 

linux 在/etc/hosts文件指定  192.168.200.1 ThinkPad-PC

3.主机名解析过程分析 (Hosts,DNS) 

 Hosts 是一个文本文件,用来记录 IP 和 Hostname(主机名)的映射关系。 DNS,Domain Name System 域名系统 是互联网上作为域名和 IP 地址相互映射的一个分布式数据库

应用实例: 用户在浏览器输入了 www.baidu.com 1) 浏览器先检查浏览器缓存中有没有该域名解析 IP 地址,有就先调用这个 IP 完成解析；如果没有,就检查DNS解析器缓存,如果有直接返回 IP 完成解析.这两个缓存,可以理解为本地解析器缓存 ，一般来说,当电脑第一次成功访问某一网站后,在一定时间内,浏览器或操作系统会缓存他的 IP 地址(DNS 解析记录).在 cmd 窗口中输入 ipconfig /displaydns DNS  ipconfig /flushdns //手动清理 dns 缓存 。 如果本地解析器缓存没有找到对应映射,检查系统中 hosts 文件中有没有配置对应的域名 IP 映射,如果有,则完成 解析并返回.  如果 本地 DNS 解析器缓存 和 hosts 文件 中均没有找到对应的 IP,则到域名服务 DNS 进行解析

![image-20220326171141053](C:\Users\王多鱼\AppData\Roaming\Typora\typora-user-images\image-20220326171141053.png)

# 10 进程管理

1.==ps== 命令是用来查看目前系统中,有哪些正在执行,以及它们执行的状况.可以不加任何参数.

![image-20220326192554601](C:\Users\王多鱼\AppData\Roaming\Typora\typora-user-images\image-20220326192554601.png)

==ps –aux|grep xxx==  System V 展示风格   USER：用户名称  PID：进程号 %CPU：进程占用 CPU 的百分比 %MEM：进程占用物理内存的百分比 VSZ：进程占用的虚拟内存大小(单位：KB) RSS：进程占用的物理内存大小(单位：KB)  TT：终端名称,缩写  STAT：进程状态,其中 S-睡眠,s-表示该进程是会话的先导进程,N-表示进程拥有比普通优先级更低的优先级,R- 正在运行,D-短期等待,Z-僵死进程,T-被跟踪或者被停止等等  STARTED：进程的启动时间 TIME：CPU 时间,即进程使用 CPU 的总时间  COMMAND：启动进程所用的命令和参数,如果过长会被截断显示

​	要求：以全格式显示当前所有的进程,查看进程的父进程. 查看 sshd 的父进程信息 ==ps -ef==是以全格式显示当前所有的进程 -e 显示所有进程.-f 全格式 ==ps -ef|grep sshd==     UID：用户ID  PID：进程 ID PPID：父进程 ID    C：CPU 用于计算执行优先级的因子.数值越大,表明进程是 CPU 密集型运算,执行优先级会降低；数值越小,表 明进程是 I/O 密集型运算,执行优先级会提高 STIME：进程启动的时间 TTY：完整的终端名称   TIME:CPU 时间   CMD：启动进程所用的命令和参数

2.终止进程 ==kill 和 killall==    若是某个进程执行一半需要停止时,或是已消了很大的系统资源时,此时可以考虑停止该进程 ==kill [选项] 进程号==(通过进程号杀死/终止进程)  killall 进程名称 (通过进程名称杀死进程,也支持通配符,这在系统因负载过大而变得很慢时很有用)  -9 :表示强迫进程立即停止

案例 1:踢掉某个非法登录用户 kill 进程号 , 如 kill 11421  2) 案例 2: 终止远程登录服务 sshd, 在适当时候再次重启 sshd 服务 kill sshd 对应的进程号; /bin/systemctl start sshd.service  3) 案例 3: 终止多个 gedit , 演示 killall gedit   4) 案例 4:强制杀掉一个终端, 指令 kill-9 bash 对应的进程号

 查看进程树  ==pstree==  pstree [选项] ,可以更加直观的来看进程信息 常用选项 -p :显示进程的 PID -u :显示进程的所属用户  案例 1：请你树状的形式显示进程的 pid pstree -p 案例 2：请你树状的形式进程的用户 ==pstree -u==

3.服务(service)管理    服务(service) 本质就是进程,但是是运行在后台的,通常都会监听某个端口,等待其它程序的请求,比如(mysqld , sshd 防火墙等),因此我们又称为守护进程,是 Linux 中非常重要的知识点.  ==service 服务名 [start | stop | restart | reload|status] 2)在CentOS7.0后很多服务不再使用服务，而是systemctl  3) service 指令管理的服务在/etc/init.d查看

请使用service指令，查看，关闭，启动网络[注意：在虚拟系统演示，因为网络连接会关闭]

指令：service network status   service network stop service network start

查看服务名：方式1：setup->系统服务   就可以看到全部。方式2：/etc/init.d看到service指令管理的服务   ls-l/etc/init.d

服务的运行级别(runlevel):  Linux 系统有 7 种运行级别(runlevel)：常用的是级别 3 和 5 运行级别 3：完全的多用户状态(有 NFS),无界面,登陆后进入控制台命令行模式 运行级别 5：X11 控制台,登陆后进入图形 GUI 模式 

![image-20220326194923650](C:\Users\王多鱼\AppData\Roaming\Typora\typora-user-images\image-20220326194923650.png)

在/etc/initab进行了简化，如下：multi-user.target：类似于运行级3  graphical .target：类似于运行级5  init 0 #查看当前默认目标，运行：systemctl get-default #设置默认target，运行：systemctl set-default TARGET.target

==chkconfig== 指令    通过 chkconfig 命令可以给服务的各个运行级别设置自启动/关闭    chkconfig 指令管理的服务在 /etc/init.d 查看     注意: Centos7.0 后,很多服务使用 systemctl 管理    chkconfig 基本语法 1) 查看服务 ==chkconfig --list [| grep xxx]== 2) ==chkconfig 服务名 --list== 3) ==chkconfig --level 5 服务名 on/off==  

案例演示 : 对 network 服务进行各种操作, 把 network 在 3 运行级别,关闭自启动 ==chkconfig --level 3 network off== ==chkconfig --level 3 network on==   ==使用细节 chkconfig 重新设置服务后自启动或关闭,需要重启机器 reboot 生效.==

4.==systemctl==设置服务的自启动状态     systemctl list-unit-files [ | grep 服务名] (查看服务开机启动状态)   ==systemctl enable 服务名==(设置服务开机启动) ==systemctl disable 服务==(关闭服务开机启动) ==systemctl is-enabled 服务名==(查询某个服务是否是自启动的) 

应用案例：查看当前防火墙的状况，关闭防火墙和重启防火墙.

==systemctl status firewalld   systemctl stop firewalld  systemctl start firewalld==   关闭或者启用防火墙后,立即生效.[telnet 测试某个端口即可] 这种方式只是==临时生效,当重启系统后,还是回归以前对服务的设置==.   如果希望==设置某个服务自启动或关闭永久生效==,要使用 ==systemctl [enable|disable] 服务名== .

5.==打开或者关闭指定端口==   ![image-20220326201331447](C:\Users\王多鱼\AppData\Roaming\Typora\typora-user-images\image-20220326201331447.png)

firewall 指令 1) 打开端口: ==firewall-cmd --permanent --add-port=端口号/协议== 2) 关闭端口: ==firewall-cmd --permanent --remove-port=端口号/协议== 3) 重新载入,才能生效 : ==firewall-cmd --reload== 4) 查询端口是否开放: ==firewall-cmd --query-port=端口/协议== 

开放 111 端口==firewall-cmd --permanent --add-port=111/tcp==  需要==firewall-cmd --reload== 3) 再次关闭 111 端口  ==firewall-cmd --permanent --remove-port=111/tcp== ; 需要 ==firewall-cmd --reload== 

6. 动态监控进程   ==top 与 ps 命令很相似,它们都用来显示正在执行的进程==,==top 与 ps 最大的不同之处,在于 top 在执行一段时间可以更新正在运行的的进程.==

top [选项]

![image-20220326202608973](C:\Users\王多鱼\AppData\Roaming\Typora\typora-user-images\image-20220326202608973.png)

![image-20220326202707516](C:\Users\王多鱼\AppData\Roaming\Typora\typora-user-images\image-20220326202707516.png)

案例 1  :监视特定用户, 比如我们监控 tom 用户 top：输入此命令,按回车键,查看执行的进程.  u：然后输入“u”回车,再输入用户名,即可   案例 2：终止指定的进程, 比如我们要结束 tom登录    top：输入此命令,按回车键,查看执行的进程.  k：然后输入“k” 回车,再输入要结束的进程 ID号    案例 3:指定系统状态更新的时间(每隔 10 秒自动更新), 默认是 3 秒   top -d 10

7 .监控网络状态    ==查看系统网络情况netstat==   ==netstat [选项]==  选项说明 ==-an 按一定顺序排列输出 -p 显示哪个进程在调用==  应用案例 请查看服务名为 sshd 的服务的信息. ==netstat -anp | grep sshd==

#11.rpm与yum

​	rpm用于互联网下载包的打包及安装工具,它包含在某些 Linux 分发版中   .它生成具有.RPM 扩展名的文件.RPM 是 RedHat Package Manager,类似 windows 的 setup.exe

rpm 包的简单查询指令  查询已安装的 rpm 列表==rpm –qa|grep xx==   看看当前系统是否安装了 firefox 指令:==rpm -qa | grep firefox==   rpm 包名基本格式 一个 rpm 包名firefox-60.2.2-1.el7.centos.x86_64   名称:firefox 版本号：60.2.2-1 适用操作系统: el7.centos.x86_64 表示 centos7.x 的 64 位系统 如果是 ==i686,i386 表示 32 位系统,noarch 表示通用== 

rpm -q 软件包名 :查询软件包是否安装 案例：==rpm -q firefox==   ==rpm -qi 软件包名== ：查询软件包信息 案例: ==rpm -qi firefox==     ==rpm -ql==软件包名 :查询软件包中的文件 比如==rpm -ql firefox==  ==rpm -qf== 文件全路径名 查询文件所属的软件包    ==rpm -qf /etc/passwd==   ==rpm -qf /root/install.log==

卸载 rpm 包： 基本语法 ==rpm -e RPM包的名称==     删除firefox软件包 ==rpm -e firefox==  ==如果其它软件包依赖于您要卸载的软件包,卸载时则会产生错误信息.==  如果我们就是要删除 foo 这个 rpm 包,可以增加参数 ==--nodeps== ,就可以强制删除,但是一般不推荐这样做,因为依 赖于该软件包的程序可能无法运行 ==rpm -e --nodeps foo==

安装 rpm 包   ==rpm -ivh RPM包全路径名称==  参数说明 i=install 安装 v=verbose提示 h=hash进度条  应用实例  演示卸载和安装 firefox 浏览器 ==rpm -e firefox== ==rpm -ivh firefox== 

yum 是一个 shell前端软件包管理器.基于 RPM 包管理,能够从指定的服务器自动下载RPM包并且安装,可以自动处理依赖性关系,并且一次安装所有依赖的软件包

查询yum 服务器是否有需要安装的软件    ==yum list|grep xx==  软件列表     安装指定的 yum 包 ==yum install xxx== 下载安装  案例 :请使用 yum 的方式来安装 firefox ==rpm -e firefox==  ==yum list | grep firefox== ==yum install firefox==

# 12.搭建Java EE 环境

![image-20220326211003600](C:\Users\王多鱼\AppData\Roaming\Typora\typora-user-images\image-20220326211003600.png)

tomcat 的安装![image-20220326211040480](C:\Users\王多鱼\AppData\Roaming\Typora\typora-user-images\image-20220326211040480.png)

![image-20220326211105257](C:\Users\王多鱼\AppData\Roaming\Typora\typora-user-images\image-20220326211105257.png)

# 13.Shell 编程

Linux运维工程师在进行服务器集群管理时,需要编写 Shell 程序来进行服务器管理.                              2) 对于 JavaEE 和 Python 程序员 ，编写一些 Shell 脚本进行程序或者是服务器的维护,比如编写一个定时备份数据库的脚本.																																 3) 大数据程序员,需要编写 Shell 程序来管理集群 

Shell是一个命令行解释器,它==为用户提供了一个向 Linux 内核发送请求以便运行程序的界面系统级程序==,==用户可以 用 Shell 来启动,挂起,停止甚至是编写一些程序==

==脚本以#!/bin/bash 开头==     ==脚本需要有可执行权限== 17.3.2 编写第一个 Shell 脚本 输出 hello world! ==vim hello.sh==   ==#!/bin/bash==  ==echo "hello,world~"==

脚本常用执行方式 

 方式 1(输入脚本的绝对路径或相对路径)  首先要赋予 helloworld.sh 脚本的+x 权限, 再执行脚本 比如 ./hello.sh 使用绝对路径 /root/shcode/hello.sh 																						方式 2(sh+脚本)   用赋予脚本+x 权限,直接执行即可.  比如 ==sh hello.sh== , 也可以使用绝对路径 

Shell 变量介绍  Linux Shell 中的变量分为==系统变量和用户自定义变量==   系统变量：$HOME , $PWD,$ SHELL,$USER ,比如： echo $HOME   显示当前 shell 中所有变量==set== 

shell 变量的定义  定义变量：==变量名=值==   撤销变量：==unset 变量==   声明静态变量：==readonly 变量,不能 unset==  

首先 #！/bin/bash  案例 1：定义变量A ==A=100==  ==输出变量需要加上$== ==echo A=$A== ==echo "A=$A"== 

案例 2：撤销变量A ==unset A== ==echo "A=$A"==    案例 3：声明静态的变量 B=2,不能unset ==readonly B=2== ==echo "B=$B"==  ==将指令返回的结果赋给变量 :<<!== ==C=’date‘  D=$(date)  echo "C=$C" echo "D=$D" !== #使用环境变量 TOMCAT_HOME ==echo "tomcat_home=$TOMCAT_HOME"==  案例 4：可把变量提升为全局环境变量,可供其他 shell 程序使用

shell 变量的定义  定义变量的规则 1) 变量名称可以由字母,数字和下划线组成,但是不能以数字开头  2) ==等号两侧不能有空格== 3) ==变量名称一般习惯为大写==  ==将命令的返回值赋给变量 1) A=`date``反引号,运行里面的命令,并把结果返回给变量A== ==2) A=$(date) 等价于反引号==

设置环境变量  ==export 变量名=变量值== ==(功能描述：将 shell 变量输出为环境变量/全局变量)== ==source 配置文件==(功能描述：让修改后的配置信息立即生效) 3) ==echo $变量名==(功能描述：查询环境变量的值)

快速入门 1) 在/etc/profile 文件中定义 TOMCAT_HOME 环境变量 2) 查看环境变量 TOMCAT_HOME 的值 3) 在另外一个 shell 程序中使用 TOMCAT_HOME ==在输出 TOMCAT_HOME 环境变量前,需要让其生效==  ==source /etc/profile==   ==shell 脚本的多行注释 :<<! 内容 !==

位置参数变量 当我们执行一个 shell 脚本,希望获取到命令行的参数信息,可以使用到位置参数变量 比如 ==./myshell.sh 100 200== , 这个就是一个执行 shell 的命令行,可以在 myshell 脚本中获取到参数信息

基本语法 $n (功能描述：n 为数字,$0 代表命令本身,$1-$9 代表第一到第九个参数,十以上的参数,十以上的参数需要用大括号包含,如${10} ) $* (功能描述：这个变量代表命令行中所有的参数,==$*把所有的参数看成一个整体)==  ==$@(功能描述：这个变量也代表命令行中所有的参数,不过$@把每个参数区分对待)==  ==$#(功能描述：这个变量代表命令行中所有参数的个数)== 

位置参数变量

![image-20220326220526771](C:\Users\王多鱼\AppData\Roaming\Typora\typora-user-images\image-20220326220526771.png)

预定义变量  shell 设计者事先已经定义好的变量,可以直接在 shell 脚本中使用 

$$ (功能描述：当前进程的进程号PID) 2) $! (功能描述：后台运行的最后一个进程的进程号(PID)) 3) $?(功能描述：最后一次执行的命令的返回状态.如果这个变量的值为 0,证明上一个命令正确执行；如果这个变量的值为非 0(具体是哪个数,由命令自己来决定),则证明上一个命令执行不正确了

 在一个 shell 脚本中简单使用一下预定义变量preVar.sh    #!/bin/bash echo "当前执行的进程 id=$$" #以后台的方式运行一个脚本,并获取他的进程号 ==/root/shcode/myshell.sh &== ==echo "最后一个后台方式运行的进程 id=$!"== ==echo "执行的结果是=$?"==

运算符 学习如何在 shell 中进行各种运算操作. 

1) ==“$((运算式))”==或==“$[运算式]”==或者==expr m + n==  2) ==注意 expr 运算符间要有空格==, 将 expr 的结果赋给某个变量,使用 `` 3) expr m - n 4) expr \*, /, %  

   <img src="C:\Users\王多鱼\AppData\Roaming\Typora\typora-user-images\image-20220326224153277.png" alt="image-20220326224153277" style="zoom:80%;" />

<img src="C:\Users\王多鱼\AppData\Roaming\Typora\typora-user-images\image-20220326224235494.png" alt="image-20220326224235494" style="zoom:80%;" />

条件判断   基本语法[  condition  \]==(注意 condition 前后要有空格)== #非空返回 true,可使用$?验证(0 为 true,>1 为 false) 		应用实例 [ hspEdu ] 返回 true [ ] 返回 false  [ condition ] && echo OK || echo notok 条件满足,执行后面的语句   																									 常用判断条件 ==1) = 字符串比较 2) 两个整数的比较 -lt 小于 -le 小于等于 little equal -eq 等于 -gt 大于 -ge 大于等于 -ne 不等于==

3) 按照文件权限进行判断 -r 有读的权限 -w 有写的权限 -x 有执行的权限 4) 按照文件类型进行判断==-f 文件存在并且是一个常规的文件 -e 文件存在 -d 文件存在并是一个目录== 

   案例 1："ok"是否等于"ok" 判断语句：使用 =     案例 2：23 是否大于等于 22 判断语句：使用 -ge 案例 3：/root/shcode/aaa.txt 目录中的文件是否存在 判断语句： 使用 -f

   <img src="C:\Users\王多鱼\AppData\Roaming\Typora\typora-user-images\image-20220326225311797.png" alt="image-20220326225311797" style="zoom: 67%;" />

流程控制  if 判断   ==if [ 条件判断式 ] then 代码 fi==     多分支  ==if [ 条件判断式 ] then 代码elif [条件判断式] then 代码fi==

注意事项：==[ 条件判断式 ],中括号和条件判断式之间必须有空格==  应用实例 ifCase.sh 案例：请编写一个 shell 程序,如果输入的参数,大于等于 60,则输出 "及格了",如果小于 60,则输出 "不及格"

<img src="C:\Users\王多鱼\AppData\Roaming\Typora\typora-user-images\image-20220326225849816.png" alt="image-20220326225849816" style="zoom:80%;" /> case 语句  基本语法 case  $变量名 in          "值 1") 如果变量的值等于值 1,则执行程序 1 ;;        "值 2") 如果变量的值等于值 2,则执行程序 2 ;;       …省略其他分支…   *)   如果变量的值都不是以上的值,则执行此程序 ;;esac

![image-20220326230042741](C:\Users\王多鱼\AppData\Roaming\Typora\typora-user-images\image-20220326230042741.png)

for 循环    for 变量 in 值 1 值 2 值 3…       do   程序/代码  done 															 案例 1 ：打印命令行输入的参数 [这里可以看出$* 和 $@ 的区别]                                                          for (( 初始值;循环控制条件;变量变化 ))  do  程序/代码 done 

案例 1 ：从 1 加到 100 的值输出显示

![image-20220326230643827](C:\Users\王多鱼\AppData\Roaming\Typora\typora-user-images\image-20220326230643827.png)

while 循环   while [ 条件判断式 ]do程序 /代码 done                 案例 1 ：从命令行输入一个数 n,统计从 1+..+ n 的值是多少?    #!/bin/bash #案例 1 ：从命令行输入一个数 n,统计从 1+..+ n 的值是多少? SUM=0 i=0 while [ $i -le $1 ] do SUM=$[$SUM+$i]  #i自增   i=$[$i+1] done echo "执行结果=$SUM" 

read 读取控制台输入   read(选项)(参数) 选项： -p：指定读取值时的提示符； -t：指定读取值时等待的时间(秒),如果没有在指定的时间内输入,就不再等待了   参数变量：指定读取值的变量名

 案例 1：读取控制台输入一个 NUM1 值  案例 2：读取控制台输入一个 NUM2 值,在 10 秒内输入. 代码:    #!/bin/bash #案例 1：读取控制台输入一个 NUM1 值   read -p "请输入一个数 NUM1=" NUM1 echo "你输入的 NUM1=$NUM1"   #案例 2：读取控制台输入一个 NUM2 值,在 10 秒内输入. read -t 10 -p "请输入一个数 NUM2=" NUM2   echo "你输入的 NUM2=$NUM2"

函数  有系统函数,也可以自定义函数    系统函数我们这里就介绍两个系统函数  basename 基本语法 功能：返回完整路径最后 / 的部分,常用于获取文件名      ==basename [pathname] [suffix]== ==basename [string] [suffix]== (功能描述：basename命令会删掉所有的前缀包括最后一个(‘/’)字符,然后将字符串显示出来. 选项suffix 为后缀,如果 suffix 被指定了,basename会将pathname或string 中的 suffix 去掉.

案例 1：请返回 /home/aaa/test.txt 的 "test.txt" 部分 ==basename /home/aaa/test.txt==  

dirname 基本语法 功能：返回完整路径最后 / 的前面的部分,常用于返回路径部分   dirname文件绝对路径(功能描述：从给定的包含绝对路径的文件名中去除文件名(非目录的部分),然后返回剩下的路径(目录的部分))   案例 1：请返回 /home/aaa/test.txt 的 /home/aaa ==dirname /home/aaa/test.txt==

**自定义函数**   基本语法   [ function ] funname[()] { Action; [return int;] }   调用直接写函数名：funname [值]   案例 1：计算输入两个参数的和(动态的获取), getSum 代码  #!/bin/bash function getSum() { SUM=$[$n1+$n2]   echo "和是=$SUM" }  read -p "请输入一个数 n1=" n1     read -p "请输入一个数 n2=" n2  getSum $n1 $n2  

**Shell 编程综合案例**   1) 每天凌晨 2:30 备份数据库hspedu 到 /data/backup/db 2) 备份开始和备份结束能够给出相应的提示信息 3) 备份后的文件要求以备份时间为文件名,并打包成 .tar.gz 的形式,比如：2021-03-12_230201.tar.gz 4) 在备份的同时,检查是否有 10 天前备份的数据库文件,如果有就将其删除.

![image-20220326234259051](C:\Users\王多鱼\AppData\Roaming\Typora\typora-user-images\image-20220326234259051.png)

/usr/sbin/mysql_db.backup.sh      

<img src="C:\Users\王多鱼\AppData\Roaming\Typora\typora-user-images\image-20220326234820048.png" alt="image-20220326234820048" style="zoom:67%;" />

<img src="C:\Users\王多鱼\AppData\Roaming\Typora\typora-user-images\image-20220326235057006.png" alt="image-20220326235057006" style="zoom: 50%;" />

# 14.Python 开发平台Ubuntu

设置 Ubuntu 支持中文   1) 单击左侧图标栏打开 Language Support 菜单,点击打开 Language Support(语言支持)选项卡. 2) 点击 Install / Remove Languages,在弹出的选项卡中下拉找到 Chinese(Simplified),即中文简体,在后面的选项框中 打勾.然后点击 Apply Changes 提交,系统会自动联网下载中文语言包.(保证 ubuntu是联网的). 3) 这时“汉语(中国)”在最后一位因为当前第一位是”English”,所以默认显示都是英文.我们如果希望默认显示 用中文,则应该将“汉语(中国)”设置为第一位.设置方法是拖动,鼠标单击“汉语(中国)”,当底色变化(表 示选中了)后,按住鼠标左键不松手,向上拖动放置到第一位. 4) 设置后不会即刻生效,需要下一次登录时才会生效

<img src="C:\Users\王多鱼\AppData\Roaming\Typora\typora-user-images\image-20220326235321279.png" alt="image-20220326235321279" style="zoom: 50%;" />

**Ubuntu 的 root 用户**  安装 ubuntu 成功后,都是普通用户权限,并没有最高 root权限,如果需要使用 root 权限的时候,通常都会在命令前面加上 ==sudo==  我们一般使用 su 命令来直接切换到 root 用户的,但是如果没有给 root 设置初始密码,就会抛出 su : Authentication failure 这样的问题.所以,我们只要==给 root 用户设置一个初始密码==就好了 给 root 用户设置密码并使用 1) 输入==sudo passwd== 命令,设定 root 用户密码. 2) 设定 root 密码成功后,输入 ==su==命令,并输入刚才设定的 root 密码,就可以切换成 root 了.提示符==$==代表一般用户, 提示符==#==代表 root用户. 3) 以后就可以使用 root 用户了 4)输入 exit 命令,退出 root 并返回一般用户  安装好 Ubuntu 后,默认就已经安装好 Python 的开发环境.  在 Ubuntu 下开发一个 Python 程序 vi hello.py [编写 hello.py]   python3 hello.py [运行 hello.py]

apt 是 Advanced Packaging Tool 的简称,是一款安装包管理工具.在 Ubuntu 下,我们可以使用 apt 命令进行软件包 的安装,删除,清理等,类似于 Windows 中的软件管理工具. 

Ubuntu 软件操作的相关命令        sudo apt-get update更新源        sudo apt-get install package 安装包  sudo apt-get remove package  删除包   sudo apt-cache search package 搜索软件包              

sudo apt-cache show package 获取包的相关信息，如说明大小版本   sudo apt-get install package --reinstall 重新安装包 sudo apt-get -f install 修复安装 sudo apt-get remove package --purge 删除包,包括配置文件等   sudo apt-get build-dep package 安装相关的编译环境  sudo apt-get upgrade 更新已安装的包  sudo apt-get dist-upgrade 升级系统  sudo apt-cache depends package 了解使用该包依赖哪些包  sudo apt-cache rdepends package 查看该包被哪些包依赖 sudo apt-get source package  下载该包的源代码

 更新 Ubuntu 软件下载地址    寻找国内镜像源 https://mirrors.tuna.tsinghua.edu.cn/ 所谓的镜像源：可以理解为提供下载软件的地方。

备份Ubuntu默认的源地址  ==sudo cp/etc/apt/sources.list /etc/apt/sources.list.backup==

更新源服务器列表 先清空 sources.list 文件复制镜像网站的地址 复制镜像网站的地址, 拷贝到 sources.list 文件

更新源 更新源地址：sudo apt-get update

Ubuntu 软件安装,卸载     案例说明：使用 apt 完成安装和卸载 vim 软件,并查询 vim 软件的信息：(因为使用了镜像网站, 速度很快) ==sudo apt-get remove vim==  ==sudo apt-get install vim==  ==sudo apt-cache show vim== //获取软件信息 

远程登录 Ubuntu    SSH 为 Secure Shell ,SSH 为建立在应用层和传输层基础上的安全协议. SSH 是目前较可靠,专为远程登录会话和其他网络服务提供安全性的协议.常用于远程登录.几乎所有 UNIX/LInux 平台都可运行 SSH.使用 SSH 服务,需要安装相应的服务器和客户端.客户端和服务器的关系：如果,A 机器想被 B 机器远程控制, 那么,A 机器需要安装 SSH 服务器,B 机器需要安装 SSH 客户端. 和 CentOS 不一样,Ubuntu 默认没有安装 SSHD 服务(使用 netstat 指令: apt install net-tools),因此,我们不能进行远程登录.

安装 SSH和启用   ==sudo apt-get install openssh-server== 执行指令后,在当前这台 Linux 上就安装了 SSH 服务端和客户端.==service sshd restart== 执行指令,就启动了 sshd 服务，会监听端口 22 

从一台 linux 系统远程登陆另外一台 linux 系统 在创建==服务器集群==时,会使用到该技术  ==ssh 用户名@IP== 例如：ssh hspedu@192.168.200.130 使用 ssh 访问,如访问出现错误.可查看是否有该文件 ==～/.ssh/known_ssh== 尝试删除该文件解决   登出命令：exit 或者 logout

#15.CentOS8.1 的使用

CentOS-8.1.1911-x86_64-dvd1.iso    https://mirrors.aliyun.com/centos/8.1.1911/isos/x86_64/

<img src="C:\Users\王多鱼\AppData\Roaming\Typora\typora-user-images\image-20220327090340425.png" alt="image-20220327090340425" style="zoom:50%;" />

# 16.日志管理

日志文件是重要的系统信息文件,记录了许多重要的系统事件,包括==用户的登录信息,系统的启动信息,系统的安全信息,邮件相关信息,各种服务相关信息==等. 2) 日志对于==安全==来说也很重要,它记录了系统每天发生的各种事情,通过日志来检查==错误发生的原因,或者受到攻击时攻击者留下的痕迹==. 3) 可以这样理解 日志是用来==记录重大事件的工具== 

 /var/log/ 目录就是系统日志文件的保存位置

![image-20220327091040913](C:\Users\王多鱼\AppData\Roaming\Typora\typora-user-images\image-20220327091040913.png)

![image-20220327091053105](C:\Users\王多鱼\AppData\Roaming\Typora\typora-user-images\image-20220327091053105.png)

应用案例 使用 root 用户通过 xshell登陆, 第一次使用错误的密码,第二次使用正确的密码登录成功 看看在日志文件/var/log/secure 里有没有记录相关信息

日志管理服务==rsyslogd==    CentOS7.6日志服务是 rsyslogd , CentOS6.x 日志服务是 syslogd	 rsyslogd 功能更强大.rsyslogd 的使用,日志文件的格式,和syslogd服务兼容的

查询 Linux 中的 rsyslogd服务是否启动 ==ps aux | grep "rsyslog" | grep -v "grep"==      查询rsyslogd 服务的自启动状态 ==systemctl list-unit-files | grep rsyslog==   配置文件：==/etc/rsyslog.conf==  编辑文件时的格式为：* .* 存放日志文件   其中第一个 * 代表日志类型,第二个*代表日志级别 

 日志类型分为： auth   ##pam产生的日志    authpriv ##ssh,ftp 等登录信息的验证信息 corn ##时间任务相关 kern ##内核 lpr ##打印 mail ##邮件 mark(syslog)-rsyslog ##服务内部的信息,时间标识  news ##新闻组 user ##用户程序产生的相关信息 uucp ##unix to nuix copy 主机之间相关的通信 local 1-7 ##自定义的日志设备 

 日志级别分为： debug ##有调试信息的,日志通信最多   info ##一般信息日志,最常用   notice ##最具有重要性的普通条件的信息  warning ##警告级别   err ##错误级别,阻止某个功能或者模块不能正常工作的信息  crit ##严重级别,阻止整个系统或者整个软件不能正常工作的信息  alert ##需要立刻修改的信息  emerg ##内核崩溃等重要信息  none ##什么都不记录  ==注意：从上到下,级别从低到高,记录信息越来越少==   

​     由日志服务 rsyslogd 记录的日志文件,日志文件的格式包含以下 4 列： 1) 事件产生的时间 2) 产生事件的服务器的主机名 3) 产生事件的服务名或程序名 4) 事件的具体信息

日志管理服务应用实例 在/etc/rsyslog.conf 中添加一个日志文件/var/log/hsp.log,当有事件发送时(如sshd 服务相关事件),该文件会接收到信息并保存. 演示重启,登录的情况,看看是否有日志保存

![image-20220327092356531](C:\Users\王多鱼\AppData\Roaming\Typora\typora-user-images\image-20220327092356531.png)

日志轮替  日志轮替就是把旧的日志文件移动并改名,同时建立新的空日志文件,当旧日志文件超出保存的范围之后,就会进行删除        日志轮替文件命名   1) centos7 使用 ==logrotate== 进行日志轮替管理,要想改变日志轮替文件名字,通过 ==/etc/logrotate.conf== 配置文件中==“dateext”== 参数：如果配置文件中有“dateext”参数,那么日志会用日期来作为日志文件的后缀,例如 “secure-20201010”.这样日志文件名不会重叠,也就不需要日志文件的改名, 只需要指定保存日志个数,删除多余的日志文件即可. 

如果配置文件中没有“dateext”参数,日志文件就需要进行改名了.当第一次进行日志轮替时,当前的“secure”日志会自动改名为“secure.1”,然后新建“secure”日志, 用来保存新的日志.当第二次进行日志轮替时,“secure.1” 会自动改名为“secure.2”, 当前的“secure”日志会自动改名为“secure.1”,然后也会新建“secure”日志,用来 保存新的日志,

==logrotate 配置文件==  /etc/logrotate.conf 为 logrotate 的全局配置文件 # rotate log files weekly     weekly # keep 4 weeks worth of backlogs, 共保存 4 份日志文件,当建立新的日志文件时,旧的将会被删除    ==rotate 4==   #create new (empty) log files after rotating old ones, 创建新的空的日志文件,在日志轮替后    ==create==   #use date作为旋转文件的后缀  dateext   #uncomment this if you want your log files compressed 日志文件是否压缩.如果取消注释，则日志会在转储的同时进行压缩    #compress  #RPM包删除日志旋转信息到这个目录，包括/etc/logrotate.d    #包含/etc/logrotate.d/目录中所有的子配置文件.也就是说会把这个目录中所有子配置文件读取进来，#下面是单独设置，优先级更高。#no packages own wtmp and btmp -- we'll rotate them here      /var/log/wtmp { monthly # 每月对日志文件进行一次轮替==create 0664 root utmp== # 建立的新日志文件,权限是 0664 ,所有者是 root ,所属组是 utmp组  ==minsize 1M== # 日志文件最小轮替大小是 1MB .也就是日志一定要超过 1MB才会轮替,否则就算时间达到 一个月,也不进行日志转储   ==rotate 1== # 仅保留一个日志备份.也就是只有 wtmp 和 wtmp.1日志保留   }    /var/log/btmp { missingok # 如果日志不存在,则忽略该日志的警告信息   ==monthly==      ==create 0600 root utmp== ==rotate 1== }   	

参数说明     daily   日志的轮替周期是每天    weekly 日志的轮替周期是每周   monthly 日志的轮替周期是每月 rotate 数字   保留的日志文件的个数,0 指没有备份    compress 日志轮替时,旧的日志进行压缩   create mode owner group 建立新日志,同时指定新日志的权限与所有者和所属组.    mail address 当日志轮替时,输出内容通过邮件发送到指定的邮件地址.    missingok 如果日志不存在,则忽略该日志的警告信息    notifempty 如果日志为空文件,则不进行日志轮替   minsize 大小 日志轮替的最小值.  size大小 日志只有大于指定大小才进行日志轮替,而不是按照时间轮替.   dateext 使用日期作为日志轮替文件的后缀.  sharedscripts 在此关键字之后的脚本只执行一次.     prerotate/endscript 在日志轮替之前执行脚本命令.   postrotate/endscript 在日志轮替之后执行脚本命令. 

**把自己的日志加入日志轮替**    1) 第一种方法是直接在/etc/logrotate.conf 配置文件中写入该日志的轮替策略 2) 第二种方法是在/etc/logrotate.d/目录中新建立该日志的轮替文件,在该轮替文件中写入正确的轮替策略,因为该目录 中的文件都会被“include”到主配置文件中,所以也可以把日志加入轮替.   **推荐使用第二种方法,因为系统中需要轮替的日志非常多,如果全都直接写 入/etc/logrotate.conf 配置文件,那么这 个文件的可管理性就会非常差,不利于此文件的维护**   4) 在/etc/logrotate.d/ 配置轮替文件一览![image-20220327094224050](C:\Users\王多鱼\AppData\Roaming\Typora\typora-user-images\image-20220327094224050.png)

应用实例  在/etc/logrotate.conf 进行配置, 或者直接在 /etc/logrotate.d/ 下创建文件 hsplog 编写如下内容

![image-20220327094306842](C:\Users\王多鱼\AppData\Roaming\Typora\typora-user-images\image-20220327094306842.png)

日志轮替机制原理 日志轮替之所以可以在指定的时间备份日志,是==依赖系统定时任务==.在 ==/etc/cron.daily/==目录,就会发现这个目录中是有 logrotate 文件(可执行),logrotate 通过这个文件依赖定时任务执行的.

![image-20220327094359151](C:\Users\王多鱼\AppData\Roaming\Typora\typora-user-images\image-20220327094359151.png)

查看内存日志    journalctl可以查看内存日志, 这里我们看看常用的指令     journalctl ##查看全部    journalctl -n 3 ##查看最新 3 条 ==journalctl --since 19:00 --until 19:10:10== #查看起始时间到结束时间的日志可加日期 journalctl -p err ##报错日志 journalctl -o verbose ##日志详细内容 journalctl _PID=1245 _COMM=sshd ##查看包含这些参数的日志(在详细日志查看) 或者 journalctl | grep sshd注意: journalctl 查看的是内存日志, 重启清空 

演示案例: 使用 journalctl | grep sshd 来看看用户登录清空, 重启系统,再次查询,看看日志有什么变化没有

# 17.linux 0.01 内核源码

内核地址：https://www.kernel.org/

 下载&解压最新版   wget https://cdn.kernel.org/pub/linux/kernel/v5.x/linux-5.8.16.tar.gz tar -zxvf linux-5.8.16.tar.gz 

linux 内核升级应用实例   将 Centos 系统从 7.6 内核升级到 7.8 版本内核(兼容性问题)

uname -a   // 查看当前的内核版本   yum info kernel -q //检测内核版本,显示可以升级的内核 yum update kernel //升级内核 yum list kernel -q //查看已经安装的内核

# 18.linux系统的备份与恢复

实体机无法做快照,如果系统出现异常或者数据损坏,后果严重, 要重做系统,还会造成数据丢失.所以我们可以使用备份和恢复技术。 linux 的备份和恢复很简单 , 有两种方式：																							 1) 把需要的文件(或者分区)用 TAR 打包就行,下次需要恢复的时候,再解压开覆盖即可 2) 使用 dump 和 restore 命令  如果 linux 上没有dump 和 restore 指令,需要先按照 yum -y install dump  yum -y install restore 

 使用 dump 完成备份     dump==支持分卷和增量备份==(所谓增量备份是指备份上次备份后 修改/增加过的文件,也称差异备份).    ==dump [ -cu] [-123456789] [ -f <备份后文件名>] [-T <日期>] [ 目录或文件系统]==   ==dump []-w W==  

 -c ： 创建新的归档文件,并将由一个或多个文件参数所指定的内容写入归档文件的开头. -0123456789： 备份的层级.0 为最完整备份,会备份所有文件.若指定 0 以上的层级,则备份至上一次备份以来修改或新增的文件, 到 9 后,可以再次轮替.    -f <备份后文件名>： 指定备份后文件名    -j : 调用 bzlib 库压缩备份文件,也就是将备份后的文件压缩成 bz2 格式,让文件更小   -T <日期>：指定开始备份的时间与日期     -u ：备份完毕后,在/etc/dumpdares 中记录备份的文件系统,层级,日期与时间等.   -t ： 指定文件名,若该文件已存在备份文件中,则列出名称    -W ：显示需要备份的文件及其最后一次备份的层级,时间,日期.   -w ：与-W 类似,但仅显示需要备份的文件.

 dump 应用案例1 将/boot 分区所有内容备份到/opt/boot.bak0.bz2 文件中,备份层级为0   ==dump -0uj -f  /opt/boot.bak0.bz2 /boot== 

dump 应用案例2  在/boot 目录下增加新文件,备份层级为“1”(只备份上次使用层次“0”备份后发生过改变的数据),==dump -1uj -f /opt/boot.bak1.bz2 /boot==   通过 dump 命令在配合 crontab 可以实现无人值守备份 

 ==dump -W== 显示需要备份的文件及其最后一次备份的层级,时间 ,日期 

查看备份时间文件  ==cat /etc/dumpdates==  

 dump 备份文件或者目录 前面我们在备份分区时,是可以支持增量备份的,如果备份文件或者目录,不再支持增量备份, 即只能使用 0 级别备份案例, 使用 dump 备份 /etc 整个目录 ==dump -0j -f /opt/etc.bak.bz2  /etc/==    #下面这条语句会报错,提示 DUMP: Only level 0 dumps are allowed on a subdirectory  dump -1j -f /opt/etc.bak.bz2 /etc/  如果是==重要的备份文件, 比如数据区,建议将文件上传到其它服务器保存==

使用 restore 完成恢复    restore 命令用来恢复已备份的文件,可以从 dump生成的备份文件中恢复原文件

 ==restore [模式选项] [选项]==      下面四个模式, 不能混用,在一次命令中, 只能指定一种.  -C ：使用对比模式,将备份的文件与已存在的文件相互对比.   -i：使用交互模式,在进行还原操作时,restors 指令将依序询问用户   -r：进行还原模式   -t : 查看模式,看备份文件有哪些文件      选项-f <备份设备>：从指定的文件中读取备份数据,进行还原操作 

应用案例1   restore 命令比较模式,比较备份文件和原文件的区别 <img src="C:\Users\王多鱼\AppData\Roaming\Typora\typora-user-images\image-20220327101051284.png" alt="image-20220327101051284" style="zoom: 80%;" />

应用案例 2 restore 命令查看模式,看备份文件有哪些数据/文件  restore -t -f boot.bak0.bz2 

应用案例3  restore命令还原模式, 注意细节：如果你有增量备份,需要把增量备份文件也进行恢复, 有几个增量备份文件, 就要恢复几个,按顺序来恢复即可.    mkdir /opt/boottmp cd /opt/boottmp restore -r -f /opt/boot.bak0.bz2 //恢复到第 1 次完全备份状态 restore -r -f /opt/boot.bak1.bz2 //恢复到第 2 次增量备份状态 应用案例4 restore 命令恢复备份的文件,或者整个目录的文件  ==restore -r -f 备份好的文件==  mkdir etctmp  cd etctmp/   restore-r-f/opt/etc.bak0.bz2

# 19. Linux可视化管理  webmin 和宝塔运维工具

Webmin 是功能强大的基于 Web 的 Unix/linux 系统管理工具.管理员通过浏览器访问 Webmin 的各种管理功能并完 成相应的管理操作.   下载：wget http://download.webmin.com/download/yum/webmin-1.700-1.noarch.rpm  安装：rpm -ivh webmin-1.700-1.noarch.rpm3) 重置密码 /usr/libexec/webmin/changepass.pl /etc/webmin root test root 是 webmin 的用户名,不是 OS 的 , 这里就是把 webmin 的 root 用户密码改成了 test 4) 修改 webmin 服务的端口号(默认是 10000 出于安全目的) vim /etc/webmin/miniserv.conf # 修改端口 5) 将 port=10000 修改为其他端口号,如 port=6666 6) 重启 webmin /etc/webmin/restart # 重启 /etc/webmin/start # 启动 /etc/webmin/stop # 停止 7) 防火墙放开 6666 端口 firewall-cmd --zone=public --add-port=6666/tcp --permanent #配置防火墙开放 6666 端口 firewall-cmd --reload # 更新防火墙配置 firewall-cmd --zone=public --list-ports # 查看已经开放的端口号 8) 登录 webmin http://ip:6666 可以访问了 用 root 账号和重置的新密码 test

宝塔面板  

安装：yum install -y wget -O install.sh http://download.bt.cn/install/install_6.0.sh && sh install.sh

如果 bt 的用户名,密码忘记了,使用 bt default 可以查看