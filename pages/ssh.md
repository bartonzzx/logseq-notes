# 免密登录
- ## vscode
- 如果使用vscode进行免密远程连接：
- 打开远程连接的插件
  ![](https://cdn.nlark.com/yuque/0/2025/png/33632868/1737264845341-a09143ae-2a36-4c03-b187-14b8d6c6843d.png){:height 606, :width 622}
- 打开ssh的配置文件
  ![](https://cdn.nlark.com/yuque/0/2025/png/33632868/1737264780682-78303eed-bf94-490f-84b4-eeb86bb9674f.png)
- 选择C:/Users那个配置文件
  ![](https://cdn.nlark.com/yuque/0/2025/png/33632868/1737264795436-12917ec9-e438-454e-be70-af41c20f2eaa.png)
- 增加IdentityFile的一行，后面的内容改为自己的"id_rsa"文件路径（注意没有pub后缀）
  ![](https://cdn.nlark.com/yuque/0/2025/png/33632868/1737264811809-7b169f4f-2f0f-492b-8683-882e01801633.png)
-
- ## 命令行
- [在windows自制ssh-copy-id的指令](https://serverfault.com/questions/224810/is-there-an-equivalent-to-ssh-copy-id-for-windows)
- 代码示例
  ```bash
  # 在linux中，生成密钥
  ssh-keygen -t rsa 
  
  # 在linux中有ssh-copy-id命令
  ssh-copy-id user@server-ip
  
  # 在windows powershell本地运行，可以自行修改文件路径，一般默认（就是一直回车...回车）
  ssh-keygen -t rsa 
  
  # 在windows powershell本地运行
  cat C:\Users\<改成你的windows用户名 或者 用tab直接补全>\.ssh\id_rsa.pub | ssh <zhixiong>@172.24.52.111 "cat >> ~/.ssh/authorized_keys"``
  ```
- 在执行ssh连接时，增加-i选项，即制定认证文件（identityfile）
  
  ```bash
  # 之后的免密ssh连接命令变为以下命令
  ssh zhixiong@172.24.52.111 -i "<你的id_rsa文件路径>"
  ```
-
- # 通过代理服务器访问目标IP
- [ssh的命令参数详解](https://www.man7.org/linux/man-pages/man1/ssh.1.html)
- 使用-o ProxyCommand，通过本地的1080端口转发(127.0.0.1:1080)
- ```bash
  ssh -o ProxyCommand="nc -x 127.0.0.1:1080 %h %p" zhixiong@172.24.52.111
  ```
-