# DeepLearning-Camp-Notes
Notes about courses Dive into Deep Learning by Mu Li

[Mu Li notes](https://github.com/MLNLP-World/DeepLearning-MuLi-Notes)

1. installation
2. keypair 
    - first go back to home directory by ```cd ~```
    - when you create the keypair, it will be downloaded on your local machine, for me, it is in ```~/Downloads```
    - move the keypair to the local ssh file location, for me, it is ```~/.ssh/```
      ```
      mv ~/Downloads/yourKeypair.pem ~/.ssh/
      ```
    - set the reading and writing permission for yourself
      ```
      chmod 600 ~/.ssh/yourKeypair.pem
      ```
    - then, set the config file to make ssh connection much easier
      ```
      # this is the ssh for aws virtual machine, 2023.4.4, work for DeepLearningMuLi
      Host 54.165.148.87
        HostName 54.165.148.87
        User ubuntu
        IdentityFile ~/.ssh/yourKeypair.pem
      ```
3. connect to virtual machine by ssh
    ```
    ssh ubuntu@54.165.148.87
    ```
```
xiexiaoran@MacBook-Pro ~ % ssh -i Desktop/xxr990610.pem ubuntu@54.165.148.87 
@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@
@         WARNING: UNPROTECTED PRIVATE KEY FILE!          @
@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@
Permissions 0644 for 'Desktop/xxr990610.pem' are too open.
It is required that your private key files are NOT accessible by others.
This private key will be ignored.
Load key "Desktop/xxr990610.pem": bad permissions
ubuntu@54.165.148.87: Permission denied (publickey).
xiexiaoran@MacBook-Pro ~ % 
```
  - [查找私有密钥并设置权限](https://docs.aws.amazon.com/zh_cn/AWSEC2/latest/UserGuide/connection-prereqs.html#connection-prereqs-private-key)
