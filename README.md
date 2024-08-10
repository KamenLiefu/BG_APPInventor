# BG_APPInventor
MIT Appinventor is more available on the market for Windows,and very few compiled on linux.
The decision was made to compile the linux version due to the need for server deployment.

# 1.Update System
```
::Install 32-bit programs
dpkg --add-architecture i386 
```
```
::Check and update dependencies
apt-get upgrade -y           
```

# 2.Environment Configure
```
sudo apt-get install -y libc6:i386 libstdc++6:i386 glibc-doc:i386 gcc-5-base:i386 gcc-6-base:i386 libgcc1:i386
```
```
sudo apt-get install -y zip unzip ant lib32z1 adb phantomjs
```
```
::Install openjdk-8-jdk or download the installation package from oracle's official website
sudo apt-get install openjdk-8-jdk 
```
![image](https://github.com/user-attachments/assets/597bfb00-1d6f-4ad3-9c9f-9959d6f08bc7)

# 3.Source Download
```
::Download the Apinvento-Souss source code
git clone https://github.com/mit-cml/appinventor-sources.git 
```
```
cd appinventor-sources
```
```
cp sample-.gitignore .gitignore
```
```
::Download the dependencies and modules needed for Apinvento Souss.
git submodule update --init #Download the dependencies and modules needed for Apinvento Souss.
```

# 4.SDK Download
```
::Download appengine-java-sdk
wget --no-verbose https://storage.googleapis.com/appengine-sdks/featured/appengine-java-sdk-1.9.68.zip 
```
```
::Unzip the downloaded zip
unzip appengine-java-sdk-1.9.68.zip 
```
```
::rename directory
mv appengine-java-sdk-1.9.68 appengine-java-sdk 
```
```
::copied to appinventor
mv appengine-java-sdk appengine-sources/appinventor 
```

# 5.Build Project
::Compile the operation, about 5~10 minutes
cd appinventor               
ant                         

# 6.Write scripts
**AppServer.sh**
```
#!/bin/sh
'/home/kali/Desktop/appinventor-sources/appinventor/appengine-java-sdk/bin/dev_appserver.sh'  --port=8888 --address=0.0.0.0 '/home/kali/Desktop/appinventor-sources/appinventor/appengine/build/war' 
```
**StartServer.sh**
```
#!/bin/sh
cd '/home/kali/Desktop/appinventor-sources/appinventor/buildserver' && ant RunLocalBuildServer
```
# 7.Result Showcase
****
<p/>
	
![屏幕截图 2024-08-07 192421](https://github.com/user-attachments/assets/de89e776-a017-468e-9151-6950e8bf552c)

<p/>
	
****
<p/>
	
![屏幕截图 2024-08-10 072732](https://github.com/user-attachments/assets/7ac79319-8e68-45a0-a706-c93983e94a16)












