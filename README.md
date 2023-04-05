# DeepLearning-Camp-Notes
Notes about course Dive into Deep Learning by Xiaoran Xie
<br>Complete course notes and code can access from [Mu Li notes](https://github.com/MLNLP-World/DeepLearning-MuLi-Notes)
#### Table of Contents
1. [Installation Machine Image](#anchor_1)<br/>
2. [sss](#anchor_14)<br/>

## Installation Machine Image<a name="anchor_1"></a>
1. install AWS machine image
    - login and search ```Amazon Machine Images (AMIs)```, then you can see the AMI catalog, since i follow Dr.Li's video, i choose the ubuntu 20.04
    - select and click the ```Launch Instance with AMI``` on the up-right side
    - tips
        - instance type
        - key pair
        - configure storage(volume storage)
            - it shows there is '0 x file system', i don't know if it will initialize a default file system for me
2. connect to server by ssh
    - when everything is done, go back to search page and check if we have the instance
    - if instance state is pending, just wait a second
    - if instance state is running, then we can check the details
        - ```Public IPv4 address``` is the IP address which we need when we use ssh
    - go to the local terminal, and go to home directory, connect to server
        ```
        ssh ubuntu@your IP address
        ```
    - if the request is denied
        ```
        xiexiaoran@MacBook-Pro ~ % ssh ubuntu@54.165.148.87
        ubuntu@54.165.148.87: Permission denied (publickey).
        ```
        keep watching... 
3. key pair 
    - first go to home directory by ```cd ~```
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
    - [查找私有密钥并设置权限](https://docs.aws.amazon.com/zh_cn/AWSEC2/latest/UserGuide/connection-prereqs.html#connection-prereqs-private-key)
