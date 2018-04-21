# Script generated with Bloom
pkgdesc="ROS - Basic grasping applications and demos."
url='http://ros.org/wiki/simple_grasping'

pkgname='ros-kinetic-simple-grasping'
pkgver='0.2.2_1'
pkgrel=1
arch=('any')
license=('BSD'
)

makedepends=('ros-kinetic-actionlib'
'ros-kinetic-catkin'
'ros-kinetic-cmake-modules'
'ros-kinetic-geometry-msgs'
'ros-kinetic-grasping-msgs'
'ros-kinetic-message-generation'
'ros-kinetic-moveit-msgs'
'ros-kinetic-pcl-ros'
'ros-kinetic-roscpp'
'ros-kinetic-sensor-msgs'
'ros-kinetic-shape-msgs'
'ros-kinetic-tf'
)

depends=('ros-kinetic-actionlib'
'ros-kinetic-geometry-msgs'
'ros-kinetic-grasping-msgs'
'ros-kinetic-message-runtime'
'ros-kinetic-moveit-msgs'
'ros-kinetic-moveit-python'
'ros-kinetic-pcl-ros'
'ros-kinetic-roscpp'
'ros-kinetic-sensor-msgs'
'ros-kinetic-shape-msgs'
'ros-kinetic-tf'
)

conflicts=()
replaces=()

_dir=simple_grasping
source=()
md5sums=()

prepare() {
    cp -R $startdir/simple_grasping $srcdir/simple_grasping
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

