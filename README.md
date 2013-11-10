## About
Application for NFC tag scanning

## Platform

The target platform to run this application is the **Raspberry Pi**. Certain functionality (linked to GPIO) will only work on that platform.

## Dependencies
The following applications should be installed on the Raspberry Pi:

### Pi4J
http://pi4j.com/<br />

#### Installation
    # wget http://pi4j.googlecode.com/files/pi4j-0.0.5.deb
    # sudo dpkg -i pi4j-0.0.5.deb

Either copy the lib files to your jre/lib/ext directory or add them to your classpath when running the application.

### RabbitMQ
http://www.rabbitmq.com/

#### Installation

Add the following line to your /etc/apt/sources.list:
<pre><code># deb http://www.rabbitmq.com/debian/ testing main</code></pre>
    # wget http://www.rabbitmq.com/rabbitmq-signing-key-public.asc
    # sudo apt-key add rabbitmq-signing-key-public.asc
    # sudo apt-get update
    # sudo apt-get install rabbitmq-server
    # sudo rabbitmq-plugins enable rabbitmq_management
	# sudo /etc/init.d/rabbitmq-server restart 

Once RabbitMQ is installed you can accesses the management interface by navigating to http://PI_ADDRESS:55672/#/ .
The interface will then prompt you for a username and password, by default both of these are guest.


## Compile project from source

### Get source

Install git first if not already present

    sudo apt-get install git

And clone this project

    git clone https://github.com/glnds/DevoxxNFC.git

### Compile

Get maven to compile the java project (and it's dependencies) with apt-get. This installation will take some time!

-sudo apt-get install openjdk-6-jdk- You'll need Java 7! Check with java -version what java is installed and with mvn -version wath java version maven uses. Use export JAVA_HOME=`/usr/libexec/java_home -v 1.7` to update JAVA_HOME to java 1.7 if needed.
    
    sudo apt-get install maven2
    
Now get the package compiled by executing below command from within the DevoxxNFC project folder. 
First run also takes time since your repo will be set up. 
    
    mvn install
   
## Run ##

usage: DevoxxNFC<br />
 -r,--room <number>     use number to specify the room<br />
 -l,--leds              enables debugging leds<br />
 -p,--platform <name>   specify then platform

    sudo java -jar DevoxxNFC.jar -r 1

 
## Architectuur

## protocol

## References
http://teaandterminals.blogspot.co.uk/2012/11/rabbit-pi.html

https://code.google.com/p/boblight/
https://github.com/adammhaile/RPi-LPD8806
https://github.com/Sh4d/LPD8806
http://learn.adafruit.com/light-painting-with-raspberry-pi/overview

