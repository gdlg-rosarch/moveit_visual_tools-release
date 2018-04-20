# Script generated with Bloom
pkgdesc="ROS - Helper functions for displaying and debugging MoveIt! data in Rviz via published markers"
url='https://github.com/davetcoleman/moveit_visual_tools'

pkgname='ros-lunar-moveit-visual-tools'
pkgver='3.3.0_1'
pkgrel=1
arch=('any')
license=('BSD'
)

makedepends=('ros-lunar-catkin'
'ros-lunar-cmake-modules'
'ros-lunar-eigen-conversions'
'ros-lunar-geometry-msgs'
'ros-lunar-graph-msgs'
'ros-lunar-moveit-core'
'ros-lunar-moveit-ros-robot-interaction'
'ros-lunar-roscpp'
'ros-lunar-roslint'
'ros-lunar-rviz-visual-tools'
'ros-lunar-std-msgs'
'ros-lunar-tf-conversions'
'ros-lunar-trajectory-msgs'
'ros-lunar-visualization-msgs'
)

depends=('ros-lunar-cmake-modules'
'ros-lunar-eigen-conversions'
'ros-lunar-geometry-msgs'
'ros-lunar-graph-msgs'
'ros-lunar-moveit-core'
'ros-lunar-moveit-ros-robot-interaction'
'ros-lunar-roscpp'
'ros-lunar-roslint'
'ros-lunar-rviz-visual-tools'
'ros-lunar-std-msgs'
'ros-lunar-tf-conversions'
'ros-lunar-trajectory-msgs'
'ros-lunar-visualization-msgs'
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

