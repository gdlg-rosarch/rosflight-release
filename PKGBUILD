# Script generated with Bloom
pkgdesc="ROS - Supporting utilities for ROSflight packages"
url='http://rosflight.org'

pkgname='ros-lunar-rosflight-utils'
pkgver='1.0.0_1'
pkgrel=1
arch=('any')
license=('BSD'
)

makedepends=('ros-lunar-catkin'
'ros-lunar-gazebo-msgs'
'ros-lunar-geometry-msgs'
'ros-lunar-roscpp'
'ros-lunar-rosflight-msgs'
'ros-lunar-rosgraph-msgs'
'ros-lunar-rospy'
'ros-lunar-sensor-msgs'
'ros-lunar-std-srvs'
)

depends=('ros-lunar-gazebo-msgs'
'ros-lunar-geometry-msgs'
'ros-lunar-roscpp'
'ros-lunar-rosflight-msgs'
'ros-lunar-rosgraph-msgs'
'ros-lunar-rospy'
'ros-lunar-sensor-msgs'
'ros-lunar-std-srvs'
)

conflicts=()
replaces=()

_dir=rosflight_utils
source=()
md5sums=()

prepare() {
    cp -R $startdir/rosflight_utils $srcdir/rosflight_utils
}

build() {
  # Use ROS environment variables
  source /usr/share/ros-build-tools/clear-ros-env.sh
  [ -f /opt/ros/lunar/setup.bash ] && source /opt/ros/lunar/setup.bash

  # Create build directory
  [ -d ${srcdir}/build ] || mkdir ${srcdir}/build
  cd ${srcdir}/build

  # Fix Python2/Python3 conflicts
  /usr/share/ros-build-tools/fix-python-scripts.sh -v 2 ${srcdir}/${_dir}

  # Build project
  cmake ${srcdir}/${_dir} \
        -DCMAKE_BUILD_TYPE=Release \
        -DCATKIN_BUILD_BINARY_PACKAGE=ON \
        -DCMAKE_INSTALL_PREFIX=/opt/ros/lunar \
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

