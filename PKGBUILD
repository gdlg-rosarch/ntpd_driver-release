# Script generated with Bloom
pkgdesc="ROS - ntpd_driver sends TimeReference message time to ntpd server"
url='http://wiki.ros.org/ntpd_driver'

pkgname='ros-lunar-ntpd-driver'
pkgver='1.2.0_1'
pkgrel=1
arch=('any')
license=('BSD'
)

makedepends=('poco'
'ros-lunar-catkin'
'ros-lunar-cmake-modules'
'ros-lunar-message-generation'
'ros-lunar-message-runtime'
'ros-lunar-roscpp'
'ros-lunar-sensor-msgs'
)

depends=('poco'
'ros-lunar-cmake-modules'
'ros-lunar-message-generation'
'ros-lunar-message-runtime'
'ros-lunar-roscpp'
'ros-lunar-sensor-msgs'
)

conflicts=()
replaces=()

_dir=ntpd_driver
source=()
md5sums=()

prepare() {
    cp -R $startdir/ntpd_driver $srcdir/ntpd_driver
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

