# Script generated with Bloom
pkgdesc="ROS - Software-in-the-loop (SIL) simulator for the ROSflight firmware"
url='http://rosflight.org'

pkgname='ros-kinetic-rosflight-sim'
pkgver='1.0.0_2'
pkgrel=1
arch=('any')
license=('BSD'
)

makedepends=('eigen3'
'gazebo'
'ros-kinetic-catkin'
'ros-kinetic-gazebo-plugins'
'ros-kinetic-gazebo-ros'
'ros-kinetic-geometry-msgs'
'ros-kinetic-roscpp'
'ros-kinetic-rosflight-firmware'
'ros-kinetic-rosflight-msgs'
)

depends=('eigen3'
'gazebo'
'ros-kinetic-gazebo-plugins'
'ros-kinetic-gazebo-ros'
'ros-kinetic-geometry-msgs'
'ros-kinetic-roscpp'
'ros-kinetic-rosflight-firmware'
'ros-kinetic-rosflight-msgs'
)

conflicts=()
replaces=()

_dir=rosflight_sim
source=()
md5sums=()

prepare() {
    cp -R $startdir/rosflight_sim $srcdir/rosflight_sim
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

