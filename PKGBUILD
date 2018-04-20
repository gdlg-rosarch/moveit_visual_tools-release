# Script generated with Bloom
pkgdesc="ROS - Helper functions for displaying and debugging MoveIt! data in Rviz via published markers"
url='https://github.com/davetcoleman/moveit_visual_tools'

pkgname='ros-kinetic-moveit-visual-tools'
pkgver='3.4.0_1'
pkgrel=1
arch=('any')
license=('BSD'
)

makedepends=('ros-kinetic-catkin'
'ros-kinetic-cmake-modules'
'ros-kinetic-eigen-conversions'
'ros-kinetic-geometry-msgs'
'ros-kinetic-graph-msgs'
'ros-kinetic-moveit-core'
'ros-kinetic-moveit-ros-robot-interaction'
'ros-kinetic-roscpp'
'ros-kinetic-roslint'
'ros-kinetic-rviz-visual-tools'
'ros-kinetic-std-msgs'
'ros-kinetic-tf-conversions'
'ros-kinetic-trajectory-msgs'
'ros-kinetic-visualization-msgs'
)

depends=('ros-kinetic-cmake-modules'
'ros-kinetic-eigen-conversions'
'ros-kinetic-geometry-msgs'
'ros-kinetic-graph-msgs'
'ros-kinetic-moveit-core'
'ros-kinetic-moveit-ros-robot-interaction'
'ros-kinetic-roscpp'
'ros-kinetic-roslint'
'ros-kinetic-rviz-visual-tools'
'ros-kinetic-std-msgs'
'ros-kinetic-tf-conversions'
'ros-kinetic-trajectory-msgs'
'ros-kinetic-visualization-msgs'
)

conflicts=()
replaces=()

_dir=moveit_visual_tools
source=()
md5sums=()

prepare() {
    cp -R $startdir/moveit_visual_tools $srcdir/moveit_visual_tools
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

