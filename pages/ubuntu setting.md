# ubuntu server
- ## 从desktop转换到server
- [convert ubuntu desktop to server ](https://askubuntu.com/questions/1313733/convert-ubuntu-desktop-to-server-edition-20-04)
- # nvidia drivers .run文件
- ## 卸载驱动
- [linux重装nvidia驱动](https://blog.csdn.net/wm9028/article/details/110268030)
- [重装nvidia driver, cuda, cudnn](https://zhuanlan.zhihu.com/p/107507007)
- ## 安装驱动
- 需要根据卸载驱动的教程关闭Nouveau驱动
- 需要gcc 12
- 一些安装过程中产生的信息：Nouveau config文件位置，driver certificate文件位置
- ``` bash
  An X.509 certificate containing the public signing key will be installed to /usr/share/nvidia/nvidia-modsign-crt-66A6E4CD.der. The SHA1 fingerprint of this certificate is:                                      
  66:A6:E4:CD:9B:C2:C4:6F:CA:F4:2E:2D:04:C0:9F:A4:CC:18:18:B6.                                                                                                                                                     
  
  This certificate must be added to a key database which is trusted by your kernel in order for the kernel to be able to verify the module signature.   
  
  The private signing key will be installed to /usr/share/nvidia/nvidia-modsign-key-66A6E4CD.key. After the public key is added to a key database which is trusted by your kernel, you may reuse the saved         
  public/private key pair to sign additional kernel modules, without needing to re-enroll the public key. Please take some reasonable precautions to secure the private key: see the README for suggestions.       
  ```
- 运行.run文件
- 导入密钥:`sudo mokutil --import /usr/share/nvidia/nvidia-modsign-crt-66A6E4CD.der`
- # nvidia drivers apt安装
- ## 临时设置apt代理
- `sudo apt -o Acquire::http::proxy="http://127.0.0.1:8080/" install  nvidia-driver-550`
-
- # nvidia container toolkit
- [nvidia container toolkit install guide](https://docs.nvidia.com/datacenter/cloud-native/container-toolkit/latest/install-guide.html)
- # nvidia cuda
-