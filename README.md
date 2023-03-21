# ffmpeg-biuld-with-x264-x265

### for ubuntu
#### install the 264 library
#### sudo apt-get install x264 libx264-dev

#### download the ffmpeg n4.4
#### git clone https://github.com/FFmpeg/FFmpeg.git -b n4.4

#### cd ffmpeg

#### Copy the patch file into the FFmpeg directory:
#### cp /path/to/sources/app-ffmpeg4-xma-patch/0001-Updates-to-ffmpeg-n4.4-to-support-Alveo-U30-SDK-v3.patch .

#### ./configure --prefix=/tmp/ffmpeg --datadir=/tmp/ffmpeg/etc  --enable-x86asm --enable-libxma2api --disable-doc --enable-libxvbm --enable-libxrm --extra-cflags=-I/opt/xilinx/xrt/include/xma2 --extra-ldflags=-L/opt/xilinx/xrt/lib --extra-libs=-lxma2api --extra-libs=-lxrt_core --extra-libs=-lxrt_coreutil --extra-libs=-lpthread --extra-libs=-ldl --disable-static --enable-shared  --enable-libx264 --enable-gpl 

#### make -j && sudo make install
