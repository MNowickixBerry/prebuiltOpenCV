# Pre-built OpenCV

This repository contains the pre-built OpenCV libraries with GStreamer for Jetson NX boards. The OpenCV is in version 4.5.5 and works with python3.

# Installation

To install just type:

`sudo dpkg -i OpenCV-4.5.5-aarch64-dev.deb`

`sudo dpkg -i OpenCV-4.5.5-aarch64-libs.deb`

`sudo dpkg -i OpenCV-4.5.5-aarch64-python.deb`

# Some comments

The prebuilt packages were created by setting a proper flag during a build:

`CPACK_BINARY_DEB:BOOL=ON`

and then manually modifying each .deb:

`dpkg-deb -R OpenCV-xxx-aarch64-dev.deb OpenCV`

`vim TEST/DEBIAN/control `

`dpkg-deb -b OpenCV OpenCV-4.5.5-aarch64-dev.deb`

I set the proper version field and changing the naming convention from `opencv-dev` to `libopencv-dev` as it was a name sought by some package installed using apt-get.
