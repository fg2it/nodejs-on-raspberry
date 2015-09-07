# Nodejs 0.12.7 release for raspberry pi
build from [0.12.7](http://nodejs.org/dist/v0.12.7/) sources and packaged with [fpm](https://github.com/jordansissel/fpm) :
```bash
wget http://nodejs.org/dist/v0.12.7/node-v0.12.7.tar.gz
tar xvfz node-v0.12.7.tar.gz
cd node-v0.12.7/
./configure 
make -j 4 #on pi 2, there are 4 cores ; run for about 30 min
mkdir /tmp/installdir
make install DESTDIR=/tmp/installdir
cd fpm -s dir -t deb -n nodejs -v 0.12.7 -C /tmp/installdir/ usr/local/lib usr/local/bin
```
