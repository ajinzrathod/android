**1st way** try this

```
yes | sdkmanager --licenses
```

If ERROR of sdkmanager is not found, goto `/usr/lib/android-sdk/cmdline-tools/bin`
```
yes | ./sdkmanager --licenses
```


-------
**2nd way**

Make sure you have installed android-sdk

1. apt-get install android-sdk

```
apt-get install android-sdk
```

2. Set environment variable ANDROID_HOME if not done yet. For example:

```
export ANDROID_HOME=/usr/lib/android-sdk
```

3. Download and install the command line tools of Android Studio from https://developer.android.com/studio#downloads. You actually don't need the full Android Studio, just the command line tools.
```
wget https://dl.google.com/android/repository/commandlinetools-linux-6609375_latest.zip
unzip commandlinetools-linux-6609375_latest.zip -d cmdline-tools
sudo mv cmdline-tools $ANDROID_HOME/
export PATH=$ANDROID_HOME/cmdline-tools/tools/bin:$PATH
```

-----------

**3rd way**

In Android Studio go to **Tools** -> **SDK Manager**.

Go to **SDK Tools** tab.

Select the **Android SDK Command-line Tools (latest)** and download by pressing **Apply**.

------

Source: Stackoverflow

https://stackoverflow.com/questions/54273412/failed-to-install-the-following-android-sdk-packages-as-some-licences-have-not

https://stackoverflow.com/questions/53994924/sdkmanager-command-not-found-after-installing-android-sdk

Credits: [Milind Modi](https://www.github.com/MilindModi)
