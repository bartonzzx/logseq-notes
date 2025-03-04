# 参考
- 查找密钥：[https://us-east-1.console.aws.amazon.com/iam/home#/users](https://us-east-1.console.aws.amazon.com/iam/home#/users)
- 官方AWS-cli认证配置：[https://docs.aws.amazon.com/cli/latest/userguide/cli-configure-files.html](https://docs.aws.amazon.com/zh_cn/cli/latest/userguide/cli-authentication-user.html)
-
- # 安装aws-cli
- ## 通过脚本安装
- ``` bash
  curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip"
  unzip awscliv2.zip
  sudo ./aws/install
  ```
- ## 通过python包安装
- ``` bash
  # 安装
  python -m pip install awscli
  # 升级
  python -m pip install --upgrade awscli
  
  ```
- # s3使用
- ## 复制文件
- ``` bash
  aws s3 cp <文件名> <s3存储库的文件名>
  ```