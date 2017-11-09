### Go FFmpeg Bindings 
This is a forked version from [github.com/3d0c/gmf](https://github.com/3d0c/gmf) without references to pkgconfig.

#### Status: `beta`
It covers very basic avformat, avcodec and swscale features.    
More bindings and cool features are coming soon.

#### Installation
##### Prerequisites
Current master branch requires `go 1.6`.  
Older versions available in branches go1.2 and go1.5.

##### Build
build lastest version of ffmpeg, obtained from [https://github.com/FFmpeg/FFmpeg](https://github.com/FFmpeg/FFmpeg)  
There is one required option, which is disabled by default, you should turn on: `--enable-shared`  

E.g.:

```sh
./configure --prefix=/usr/local/ffmpeg --enable-shared --enable-libvorbis
make -j4
make install
```

Run exporting CGO paths:

```sh
export CGO_CFLAGS="-I/usr/local/ffmpeg/include"
export CGO_LDFLAGS="-L/usr/local/ffmpeg/lib -lavcodec -lavutil -lavformat -lavdevice -lavfilter -lswresample -lswscale"
```

Then just run

```sh
go get github.com/aimlabmu/gmf
```

#### Usage
Please see [examples](examples/) and tests. 

#### Credits
Abandoned project on code.google.com/p/gmf. Original code is available at [github.com/3d0c/gmf](https://github.com/3d0c/gmf) in intitial commit from 03 Apr 2013.
