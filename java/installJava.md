java -version

## install java     
https://linuxize.com/post/install-java-on-debian-9/     

## Set the Default Version    
sudo update-alternatives --config java

## set java home    
https://linuxize.com/post/install-java-on-raspberry-pi/     

Once you found the path of the Java installation, open the /etc/environment file:
sudo nano /etc/environment
Assuming you want to set JAVA_HOME to OpenJDK 11, add the following line, at the end of the file:

/etc/environment
JAVA_HOME="/usr/lib/jvm/java-11-openjdk-armhf/bin/java"
Copy
For changes to take effect on your current shell you can either log out and log in or run the following source command:

source /etc/environment
To verify that the JAVA_HOME variable is set, type:

echo $JAVA_HOME  

## Note:        
- pretty easy to install java on raspberry pi       
- cannot install java on arm chromebook(debian 9)       

