npm install -g ionic@1.4.0
npm install -g cordova@5.0.0
apt-get install -y -q python-software-properties software-properties-common
add-apt-repository ppa:webupd8team/java -y
apt-get update
apt-get install oracle-java8-installer
apt-get install oracle-java8-set-default
apt-get install wget vim
   apt-get install -y --force-yes expect ant wget libc6-i386 lib32stdc++6 lib32gcc1 lib32ncurses5 lib32z1 qemu-kvm kmod 
cd /opt
wget --output-document=android-sdk.tgz http://dl.google.com/android/android-sdk_r24.4.1-linux.tgz
tar xzf android-sdk.tgz 
rm -f android-sdk.tgz
echo "export ANDROID_HOME=/opt/android-sdk-linux" >> ~/.bash_profile 
echo "export PATH=$PATH:/opt/android-sdk-linux/tools:/opt/android-sdk-linux/platform-tools" >> ~/.bash_profile 
source ~/.bash_profile
android update sdk --all --no-ui --filter platform-tools,tools,build-tools-22,android-22,extra-android-support,extra-android-m2repository,extra-google-m2repository
docker commit 1e6c66548ca0 ubuntu:ionic
docker save ubuntu:ionic > ubuntu_angularjs_ionic.tar




Epay.ph
docker load < ubuntu_angularjs.tar
docker run -it --rm -p 8080:80 -v ~/Documents/Sites/epay.ph/:/var/www/html/ ubuntu:angularjs
CTRL-P-Q = close and running
docker attach 10224ce024f6
docker ps
