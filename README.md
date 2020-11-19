https://philenius.github.io/software%20quality/2020/04/09/installing-spin-on-ubuntu-19.html


Following these steps, I managed to run Spin model checker on Ubuntu:

Download the Spin binary from Github and extract it to your favorite installation directory:
INSTALL_DIR=/opt
cd $INSTALL_DIR

wget https://github.com/nimble-code/Spin/archive/version-6.5.2.tar.gz
tar xfz version-6.5.2.tar.gz

Build the Spin binary:
sudo apt-get install -y build-essential byacc flex graphviz
cd $INSTALL_DIR/Spin-version-*/Src
make
sudo cp spin /usr/bin/

This is how you can execute a simple model written in Promela, the modeling language for Spin, from the command line:
spin $INSTALL_DIR/Spin-version-*/Examples/hello.pml

The usage of iSpin requires the installation of tk, a graphical user interface toolkit:
sudo apt-get install -y tk
cd $INSTALL_DIR/Spin-version-*/optional_gui/
./ispin.tcl
