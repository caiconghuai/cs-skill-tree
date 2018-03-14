# Linux

## Linux的文件权限与目录配置

### 1. 用户与用户组

- 文件所有者
- 用户组
- 其他人

### 2. 文件权限

- #### **Linux文件属性**

  - **查看** `ls -al` `-rw-r--rr 1 root root 42304 Sep 4 18:26 install.log`

    - 第一个字符代表这个文件是“目录、文件或链接文件”
      - [d] 目录
      - [-] 文件
      - [l] 连接文件
      - [b] 接口设备
      - [c] 串行端口设备
    - 接下来三组三个字符
      - 第一组 “文件所有者的权限”
      - 第二组 “同用户组的权限”
      - 第三组 “其他非本用户组的权限”
    - 第二列表示文件的连接数
    - 第三列 这个文件的“所有者账号”
    - 第四列 这个文件的所属用户组
    - 第五列 文件的容量大小
    - 第六列 创建日期或修改日期
    - 第七列 文件名

  - **修改权限**

    - `chgrp` 改变文件所属用户组
    - `chown` 改变文件所有者
    - `chmod` 改变文件的权限

  - **目录与文件的权限意义**

    - |      |       文件        |                    目录                    |
      | :--: | :-------------: | :--------------------------------------: |
      |  r   |      读取此文件      |              具有读取目录结构列表的权限               |
      |  w   |     修改文件内容      | 具有更改该目录结构列表的权限:<br />新建新的文件与目录；<br />删除已经存在的文件与目录；<br />将已存在的文件或目录进行重命名;<br />转移该目录的文件、目录位置 |
      |  x   | 该文件具有可以被系统执行的权限 |             用户能否进行该目录称为工作目录              |

  - **Linux文件种类与扩展名**

    - |         |                                          |
      | :-----: | :--------------------------------------: |
      |  普通文件   |            纯文本文件；二进制文件；数据格式文件            |
      |   目录    |                   [d]                    |
      |  连接文件   |                   [l]                    |
      | 设备与设备文件 | 在/dev目录下：**块设备文件/dev/sda；字符设备文件[c] 串行端口** |
      |   套接字   |          网络上的数据连接 [s] /var/run           |
      |   管道    |          解决多个程序同时访问一个文件所造成的错误问题          |

  - **目录树**

    - |                              |                            |
      | :--------------------------: | :------------------------: |
      |              /               |           开机系统有关           |
      | /usr(Unix software resourse) |         软件安装、执行有关          |
      |        /var（variable）        |         与系统运作过程有关          |
      |             /bin             |     单用户维护模式下还能够被操作的命令      |
      |            /boot             |         开机会使用到的文件          |
      |             /dev             |            设备文件            |
      |             /etc             |          系统的配置文件           |
      |            /home             |           用户主文件夹           |
      |             /lib             |         开机时用到的函数库          |
      |            /media            |           可删除的设备           |
      |             /mnt             |          暂时挂载的设备           |
      |             /opt             |         第三方软件放置的目录         |
      |            /root             |         系统管理员的主文件夹         |
      |            /sbin             | 开机过程中所有的，开机、修复、还原系统所需要的命令  |
      |             /srv             |  网络服务启动之后，这些服务所需要去用的数据目录   |
      |             /tmp             |            临时目录            |
      |         /lost+found          | 当文件系统发生错误，将一些丢失的片段放置在这个目录下 |
      |            /proc             |           虚拟文件系统           |
      |             /sys             |     虚拟文件系统，记录与内核相关的信息      |

      ​

  ​