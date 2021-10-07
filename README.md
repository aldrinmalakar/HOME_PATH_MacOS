# HOME_PATH_MacOS

### This ReadMe is my note to remind me how to setup Home Paths on Mac OS Big Sur with ~/.zshrc instead of ~/.bash_profile.

For the Mac OS versions where Bash Profile doesn't work, but zshrc does, this is how it worked for me. 

All the downloads were VIA Homebrew but Java JDK. JDK was downloaded from official site, and installed manualy. 
To initiate, open *Terminal* and type in
```shell 
vim ~/.zshrc
```
Then press *I* to go into edit mode. and then add the following line[s] for JDK, Android SDK, and Maven
```shell
#Java Home Path
export JAVA_HOME=$(/usr/libexec/java_home)
export PATH=${JAVA_HOME}/bin:$PATH

#Android Home Path
export ANDROID_HOME=$HOME/Library/Android/sdk/
export PATH=$PATH:$ANDROID_HOME/tools
export PATH=$PATH:$ANDROID_HOME/platform-tools

#Maven Home Path
export MAVEN_HOME=~/apache-maven-3.8.3
export PATH=$PATH:$MAVEN_HOME/bin
```
_[note]_ Maven path is version dependant. 

Once those texts are added, exit out of the editor by pressing *ESC* key. type 
```shell
:wq!
```
and press *ENTER*. Type 
```shell
source ~/.zshrc
```
This will save the edits and then it should work. 

Versions can be check with

```shell
echo $ANDROID_HOME
/Users/aldrinmalakar/Library/Android/sdk/

echo $JAVA_HOME
/Library/Java/JavaVirtualMachines/jdk-11.0.12.jdk/Contents/Home

echo $MAVEN_HOME
/Users/aldrinmalakar/apache-maven-3.8.3
```


