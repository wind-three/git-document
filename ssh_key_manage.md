
git config 命令

    查看git的配置
    git config --list 
    
    全局配置
    git config --global user.name "your name"
    git config --global user.email "yourmail@gmail.com"
    
    当前项目的配置
    git config user.name "your name"
    git config user.email "yourmail@gmail.com"
    

ssh 命令

    ssh-keygen -t rsa -C "yourmail@gmail.com"
    生成 ssh key 这时在 ~/.ssh/ 目录下 有2个文件 id_rsa id_rsa.pub
    
    为了让SSH识别新的私钥，需将其添加到SSH agent中：
    ssh-add ~/.ssh/id_rsa
    可以查看 id_rsa.pub 公钥 将内容放到服务器上
    
    衍生命令：
    ssh -T  测试
    ssh-add ~/.ssh/filename //添加
    ssh-add -l //列表
    ssh-add -D //删除添加的
    
多个 ssh key 时如何 弄
    
    ssh-keygen -t rsa -C "yourmail@gmail.com" 生成密钥时 重命名一下啊
    在~/.ssh/ 目录下 会有多对密钥
    
    然后 添加私钥  ssh-add ~/.ssh/私钥名称 
    查看 ssh agent 重的私钥  ssh-add -l
    
    添加配置文件
    ~/.ssh/config 没有创建文件
    
    #######################################
    
    # gitlab
        Host git.iboxpay.com
        HostName git.iboxpay.com  //这里填你们公司的git网址即可
        PreferredAuthentications publickey
        IdentityFile ~/.ssh/id_rsa_gitlab
        User zhangjun
    
    # github
    Host github.com
        HostName github.com
        PreferredAuthentications publickey
        IdentityFile ~/.ssh/id_rsa_github
        User ZJsnowman 
        
    ##################################
    
    参考： http://www.jianshu.com/p/f7f4142a1556
    
    
    
    
    
    
    