# Feature_Descriptor_mcptam
      This repository contains addon files for MCPTAM. More information about the addon can be found in the paper. If you use the addons, consider citing it.<br>

      @Article{JingdongCalibration,
      Title={{An Online Automatic Calibration Method Based on Feature Descriptor for Non-Overlapping Multi-Camera System},
      Author={Long Zhang, Jingdong Zhang, Wen Zhang,  Chaofan Zhang, Yong Liu},
      Journal={IEEE International Conference on Robotics and Biomimetics (ROBIO)},
      Year={2018}
      }

# Prerequisites Installation
#!/bin/bash
cd ~
mkdir mcptam_deps
cd mcptam_deps

#TooN
wget http://www.edwardrosten.com/cvd/TooN-2.2.tar.gz
tar vxf TooN-2.2.tar.gz
cd TooN-2.2
./configure
make
make install
cd ..

#libcvd
wget http://www.edwardrosten.com/cvd/libcvd-20150407.tar.gz
tar vxf libcvd-20150407.tar.gz
cd libcvd-20150407
export CXXFLAGS=-D_REENTRANT
./configure --without-ffmpeg
make
make install
cd ..

#gvars3
wget http://www.edwardrosten.com/cvd/gvars-3.0.tar.gz
tar vxf gvars-3.0.tar.gz
cd gvars-3.0
./configure --disable-widgets
make
make install
cd ../../

rm -rf mcptam_deps
