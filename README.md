# Installing the ambient

### Installing JAVA
```
sudo apt install openjdk-8-jre openjdk-8-jdk
```

### Installing Android Studio
```
sudo snap install android-studio
```

### Configure terminal
Can be ~/.zshrc

```
export ANDROID_HOME=$HOME/Android/Sdk
export PATH=$PATH:$ANDROID_HOME/tools
export PATH=$PATH:$ANDROID_HOME/tools/bin
export PATH=$PATH:$ANDROID_HOME/platform-tools
# Configure android emulator to run directly in terminal.
function emulator { ( cd "$(dirname "$(whence -p emulator)")" && ./emulator "$@"; ) }
# Set alias to shorten command and also fix the side-effect
alias emu="$ANDROID_HOME/tools/emulator"
```

### Add devices
```
sdkmanager "system-images;android-27;google_apis;x86"
```

```
avdmanager create avd -n doo1 -k "system-images;android-27;google_apis_playstore;x86" --device 'Nexus 5X'
```
