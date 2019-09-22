# ROS代码版本管理
#### RoboWare Studio 提交代码到 GitHub教程

<hr>

## 目录
### 




### 一、创建本地git仓库  
   * #### 首先使用RoboWare Studio 新建 workspace ，并进入新建的工作空间  
   ```
        cd ~/catkin_ws
   ```
   * #### 初始化本地仓库
   ```
        git init 
   ```  
   #### 此时终端提示建立好了一个空仓库，并建立了一个 .git 的隐藏文件
   ```
        Initialized empty Git repository in /home/user/catkin_ws/.git/
   ```  
### 二、创建Github远程仓库
   * 使用SSH加密方式构建与云端仓库的连接，首先创建SSH Key：
   ``` 
   cd
   ssh-keygen -t rsa -C "youremail@example.com"
   gedit .ssh/id_rsa.pub
   ```
   打开这个公钥，复制里面的东西，待用。
   * 设置GitHub SSH-Key
   * 进入GitHub页面，点击 右上角菜单 --> Setting --> SSH and GPG key --> New SSH key
   * 随意填写一个 Title， 并将上面复制的 Key 粘贴在 Key方框中。  
### 三、在GitHub中新建一个仓库
### 四、关联RoboWare Studio 与 GitHub
   * #### 关联本地与云端
   ``` 
   cd ~/catkin_ws
   git remote add origin git@github.com:usrname/myros.git
   ```
   * #### 添加过滤规则，避免上传不必要文件
   ``` 
    cd ~/catkin_ws
    gedit .gitignore
```
 ##### 打开文件后填入：
``` 
    build/
    devel/
    devel_isolated/
    el/
    el_isolated/
    install/   
   ```  
   * 尝试添加代码到本地仓库，执行：  
   `git add -A`
   > -A是自动添加全部要上传到仓库的文件,添加完后输入提交到本地仓库。  
   
   ```
    git commit -m "test"
   ```  
   > 执行此命令后，将本地与远程分支对应
   ```
    git push --set-upstream origin master
```  
   > 此时本地库已经同步到GitHub上去了.  
### 五、在RoboWare Studio 中快速提交代码上传
   * #### 更改下文件，保存一下，就可以看到这里发生了变化：
   ![快速代码提交](https://github.com/JinghuiChan/GitHub/blob/master/Pics/RobowareToGithub/roboware2github1.png)
   
> 这个base就是我们刚改动的文件。  

> 在消息栏中填入本次改动的备注（随便写），点对号或ctrl+enter进行提交（对应命令：git commit）。  

>之后在旁边的省略号下拉栏中点击推送，就可以把改动同步到云端了。（对应命令：git push origin）  
   
    
   
 