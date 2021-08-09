# useful memories
short personal reusable tips

#How to setup android app compilation enviroment on ubuntu 18

Requirements: 
1. JDK
2. SDK
3.nginx

# 1. Java JDK installation on linux
```
$ sudo apt-get install openjdk-11-jre
$ sudo apt-get install openjdk-8-jre
$ sudo apt-get install openjdk-8-jdk
```
If you desire a specific java version you can switch with:
```
$ sudo update-alternatives --config java
```
To confirm check current java version: 

$ java -version



# 2. SDK installation.

Install package using snap https://snapcraft.io/androidsdk

```
sudo snap install androidsdk
```

Install packages
```
androidsdk packages [options]
```
The packages argument is an SDK-style path as shown with the --list command, wrapped in quotes (for example, "build-tools;29.0.0" or "platforms;android-28"). You can pass multiple package paths, separated with a space, but they must each be wrapped in their own set of quotes.

For example, here's how to install the latest platform tools (which includes adb and fastboot) and the SDK tools for API level 28:
```
androidsdk "platform-tools" "platforms;android-28"
```
update all install packages: 
```
androidsdk --update
```

# Export the Android SDK path 
```
export ANDROID_HOME=$HOME/AndroidSDK

export PATH=$PATH:$ANDROID_HOME/tools/bin

export PATH=$PATH:$ANDROID_HOME/platform-tools
```
Save paths to environment:
```
source ~/.bashrc
```

Accept android sdk licences to use build tools
```
sudo androidsdk --licenses
```
#build android app 

Give gradlew permission :
```
chmod 777 gradlew
```
Build debug app:
```
./gradlew assembleDebug
```


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
Reload nginx config : 
```
nginx -s reload
```
