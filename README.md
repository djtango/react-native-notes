#React Native

v.1  
_it sucks_  

Getting an app running:  
_have you got android studio?_  
_have you got a compatible JDK?_  
_have you got KVM enabled in your bios for android emulation?_  
```
dnf -y install qemu-kvm libvirt virt-install bridge-utils #for fedora
```
_have you got a virtual android device configured?_  
_is it running Android 7?_  
_have you got your virtual android device running?_  


*START*  

Get watchman - it's not a _recommended_ add-on it is a *dependency* (FU Facebook for wasting an hour of my time).

Build from source:
```
$ git clone https://github.com/facebook/watchman.git
$ cd watchman
$ git checkout v4.7.0  # the latest stable release
$ git checkout -b v4.7.0
$ ./autogen.sh
$ ./configure
$ make
$ sudo make install
```

Make sure `max_user_watches` is setup correctly with enough watch space:
```
echo 65536 | sudo tee -a /proc/sys/fs/inotify/max_user_watches
```

Clear watchman if server:
```
watchman shutdown-server
```

If you failed some stuff, clear your react-native server cache:
```
react-native start --reset-cache
```

Now you can start your project, cd into your projects folder and run:
```
react-native init HaveMercyLetThisProjectBuild
```

cd HaveMercyLetThisProjectBuild
react-native run-android
