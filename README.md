LXDE virtual desktop running in Docker container on Bluemix.

Prelim : make sure you have a Bluemix account, the cf CLI installed with the ice plugin.

Use VNC Viewer to access the desktop with 'passw0rd' as the password. Open an SSH connection to the container and tunnel the local 5900 port to the remote one (i cannot connect to port 5900 directly). 

To start the container, simply type :
```
[prompt]> cf ic run -p 22:22 -p 5900:5900 -m 256 --name "Virtual Desktop" registry.ng.bluemix.net/besnard_mobi/desktop-light:latest 
```

To change VNC password :
```
[prompt]> x11vnc -storepasswd $PASS /home/default/.x11vnc/passwd
```

Minimal desktop screenshot :

<img src="https://github.com/besn0847/desktop-mini/raw/master/desktop-mini.png" width=400/>
