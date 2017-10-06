# Face tracking functional software for Linux

- compiles correctly and runs with the latest version of open cv, gcc 6.3 on Ubuntu 17.04
- no GUI

### Build script:
```bash
# pre-requisites for Open CV
apt-get install libgtk2.0-dev ffmpeg
wget https://github.com/opencv/opencv/archive/3.3.0.tar.gz
tar -xvf 3.3.0.tar.gz
cd opencv-3.3.0/
mkdir installation
mkdir build && cd build
cmake -DCMAKE_INSTALL_PREFIX=./installation -DCMAKE_BUILD_TYPE=Debug       -DENABLE_AVX=ON       -DENABLE_FAST_MATH=ON       -DENABLE_SSE=ON       -DENABLE_SSE2=ON       -DENABLE_SSE3=ON       -DENABLE_SSE41=ON       -DENABLE_SSE42=ON       -DENABLE_SSSE3=ON ..
make && make install
cd ../../face-analysis-sdk/

#pre-requisites for face sdk
apt-get install libobjc-5-dev libgnustep-base1.24 libgnustep-base-dev
mkdir build
cd build
cmake -DOpenCV_PREFIX=../opencv-3.3.0/installation -DFFMPEG=/usr/local/bin/ffmpeg ..
make
```


-----------------------
The face tracking component is based on the publication: 
J. Saragih, S. Lucey and J. Cohn, "Deformable Model Fitting by
Regularized Landmark Mean-Shift", IJCV 2011.

The expression transfer component is based on the publication:
J. Saragih, S. Lucey and J. Cohn, "Real-time Avatar Animation from a
Single Image", AFGR Workshop 2011.

If you use the SDK, we ask that you reference the following paper:
M. Cox, J. Nuevo, J. Saragih and S. Lucey, "CSIRO Face Analysis SDK",
AFGR 2013.