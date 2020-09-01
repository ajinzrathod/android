#### Open Link: https://developer.android.com/studio#command-tools

I am installing command line tools in $HOME directory but it is not mandatory

## Create Directory
```
cd ~
mkdir android-sdk
cd android-sdk
mkdir cmdline-tools
cd cmdline-tools
```

**sdkmanager lives inside** `cmdline-tools/tools/bin`


When you click on any "SDK tool package" of any OS,
you will find something like this:

```
commandlinetools-linux-6609375_latest.zip
wget https://dl.google.com/android/repository/<commandlinetools-linux-*.zip>
unzip <commandlinetools-linux-*.zip>
```


But `cmdline-tools` should not be set as `ANDROID_HOME`
Because later, when updating Android SDK, or installing more packages,
the other packages will be placed under `ANDROID_HOME`, but not under `cmdline-tools`



## Edit ~/.bashrc File
Add SDK tools directory in PATH environment variable to make executable available globally.
Add below line either in `~/.bashrc` or `~/.profile` file to make it permanent.

Type: `vim ~/.bashrc`

```
export ANDROID_HOME=/home/"user"/android-sdk
export PATH=${PATH}:$ANDROID_HOME/cmdline-tools/tools/bin:$ANDROID_HOME/platform-tools
export ANDROID_HOME=/home/ajinzrathod/android-sdk/
export PATH=${PATH}:$ANDROID_HOME/cmdline-tools/tools/bin/:$ANDROID_HOME/platform-tools/
```
Now got to android-sdk: `cd android-sdk`


**NOTE**: _well in first attempt sdkmanager command didnt found for me 
So I closed the terminal and reopened it_



## Install Packages
After that use the sdkmanager to list and install the packages needed:

`sdkmanager "platform-tools" "platforms;android-27" "build-tools;27.0.3"`



## Final Look
The final, complete ANDROID_HOME directory structure should look like below,
consist of quite a few sub-directories: 

`build-tools`, `cmdline-tools`, `emulator`, `licenses`, `patcher`, `platform-tools`, `platforms`, `tools`
You can easily point out that "build-tools" and "cmdline-tools" are siblings,
all resides inside the parent ANDROID_HOME.

Hence Sdkmanager path is already set it will be accessible from anywhere:
`sdkmanager --version`



## Not Working ?
In case sdkmanager is not working, try this

```
cd android-sdk/cmdline-tools/tools/bin
./sdkmanager --version
```

**OUTPUT-DEMO**

4.0.1

If `./sdkmanager` is working, but `sdkmanager` is NOT working, the issue is with the PATH
