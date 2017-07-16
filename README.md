# docker-gui-firefox
Use X11 to run GUI app on docker <br/>
1.First pull in Ubuntu:14.04, then install firefox by running: apt-get update && apt-get install firefox(can also build from a Dockerfile) <br/>
2.Install XQuartz(since X11 is no longer included directly in mac os)<br/>
Open a X server by running open -a XQuartz <br/>
3.Install socat: Socat is a command line based utility that establishes two bidirectional byte streams and transfers data between them<br/>
Run socat TCP-LISTEN:6000,reuseaddr,fork UNIX-CLIENT:\"$DISPLAY\" <br>
4.In mac, YOUR_LOCAL_IP can come from ifconfig en0<br/>
docker run -d -e DISPLAY=YOUR_LOCAL_IP:0 firefox_dev:1.0 firefox<br/>
