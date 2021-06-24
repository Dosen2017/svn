# svn创建新仓库的步骤
### 创建仓库
    1.进入svn安装目录：cd /data/svn
    2.执行创建新仓库的命令：svnadmin create control
### 修改配置文件
    1.进入到创建的仓库目录：cd /data/svn/control
    2.对conf/authz, conf/passwd,conf/svnserve.conf三个配置文件修改
        authz 修改如下：
                      [groups]
                      pm=Sds1
                      jyhy_data=Whp1,Whp2
                      [/]
                      @pm=rw
                      @jyhy_data=rw
                      Whp3=rw
                      *=rw
        passwd 修改如下：
                    [users]
                    Sds1 = sdsJy1234
                    Whp1 = whpJy6234
                    Whp2 = whpJy26234
                    Whp3 = whpJy36234
        svnserve.conf 修改如下：
                    [general]
                    anon-access = none
                    auth-access = write
                    password-db = passwd
                    authz-db = authz
                    realm = /data/svn/control
### 编写脚本重启svn
    1.关掉svn进程：
    ps -aux | grep svn
    kill 18648
    或
    killall svnserve
    2.启动svn进程
    svnserve -d -r /data/svn



