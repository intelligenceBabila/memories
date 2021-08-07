# useful memories
short personal reusable tips

#How to setup android app compilation enviroment on ubuntu 18

Requirements: 
1. JDK
2. SDK

# 1. Java JDK installation on linux
```
$ sudo apt-get install openjdk-11-jre
```
If you desire a specific java version you can switch with:
```
$ sudo update-alternatives --config java
```
To confirm check current java version: 

$ java -version

# 2. SDK installation.



# Setting nginx to listen & forward to node server 

```
server {
    listen       ...;
    ...
    location / {
        proxy_pass http://127.0.0.1:8080;
    }
    ...
}
```


