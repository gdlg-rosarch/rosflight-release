# Script generated with Bloom
pkgdesc="ROS - Package for interfacing to the ROSflight autopilot firmware over MAVLink"
url='http://rosflight.org'

pkgname='ros-kinetic-rosflight'
pkgver='1.0.0_2'
pkgrel=1
arch=('any')
license=('BSD'
)

makedepends=('boost'
'eigen3'
'git'
'pkg-config'
'ros-kinetic-catkin'
'ros-kinetic-eigen-stl-containers'
'ros-kinetic-geometry-msgs'
'ros-kinetic-roscpp'
'ros-kinetic-rosflight-msgs'
'ros-kinetic-sensor-msgs'
'ros-kinetic-std-msgs'
'ros-kinetic-std-srvs'
'ros-kinetic-tf'
'yaml-cpp'
)

depends=('boost'
'eigen3'
'ros-kinetic-eigen-stl-containers'
'ros-kinetic-geometry-msgs'
'ros-kinetic-roscpp'
'ros-kinetic-rosflight-msgs'
'ros-kinetic-sensor-msgs'
'ros-kinetic-std-msgs'
'ros-kinetic-std-srvs'
'ros-kinetic-tf'
'yaml-cpp'
)

conflicts=()
replaces=()

_dir=rosflight
source=()
md5sums=()

prepare() {
    cp -R $startdir/rosflight $srcdir/rosflight
}

build() {
  # Use ROS environment variables
  source /usr/share/ros-build-tools/clear-ros-env.sh
  [ -f /opt/ros/kinetic/setup.bash ] && source /opt/ros/kinetic/setup.bash

  # Create build directory
  [ -d ${srcdir}/build ] || mkdir ${srcdir}/build
  cd ${srcdir}/build

  # Fix Python2/Python3 conflicts
  /usr/share/ros-build-tools/fix-python-scripts.sh -v 2 ${srcdir}/${_dir}

  # Build project
  cmake ${srcdir}/${_dir} \
        -DCMAKE_BUILD_TYPE=Release \
        -DCATKIN_BUILD_BINARY_PACKAGE=ON \
        -DCMAKE_INSTALL_PREFIX=/opt/ros/kinetic \
        -DPYTHON_EXECUTABLE=/usr/bin/python2 \
        -DPYTHON_INCLUDE_DIR=/usr/include/python2.7 \
        -DPYTHON_LIBRARY=/usr/lib/libpython2.7.so \
        -DPYTHON_BASENAME=-python2.7 \
        -DSETUPTOOLS_DEB_LAYOUT=OFF
  make
}

package() {
  cd "${srcdir}/build"
  make DESTDIR="${pkgdir}/" install
}

