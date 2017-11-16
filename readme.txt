* Required packages
xorg-x11-server-Xvfb nodejs npm firefox ImageMagick festival festvox* xdotool jq fftw-devel fftw2-devel

* Remove already existing R
yum remove R R-core

* Node.js
npm install -g ionic@1.6.1
npm install -g cordova@5.1.1

WRONG_FILE=/usr/lib/node_modules/ionic/node_modules/ionic-app-lib/lib/config.js
cat $WRONG_FILE| perl -pe "s/CONFIG_FILE:.*/CONFIG_FILE: \'.\/ionic\/ionic.config\',/g" > /tmp/config.js
cp -v /tmp/config.js /usr/lib/node_modules/ionic/node_modules/ionic-app-lib/lib/config.js


* JPM
npm install -g jpm



* install R-2.15.2
cd madface/R
./R-compile.sh


* R packages
bcp
entropy
rimage



* Firefox configuration
 Install AutoAuth addon

 Import certificate -> check "do not ask"
 about:config --> browser.sessionstore.restore_from_crash --> false

 about:telemetry --> enable

 (this is for madfox, because madfox is an unsigned package for now)
 about:config --> xpinstall.signatures.required --> false

 max_script_run_time

 Install Skip Cert Error addon

