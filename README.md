https://philenius.github.io/software%20quality/2020/04/09/installing-spin-on-ubuntu-19.html<br />


Following these steps, I managed to run Spin model checker on Ubuntu:<br />

Download the Spin binary from Github and extract it to your favorite installation directory:<br />
INSTALL_DIR=/opt<br />
cd $INSTALL_DIR<br />

wget https://github.com/nimble-code/Spin/archive/version-6.5.2.tar.gz<br />
tar xfz version-6.5.2.tar.gz<br />

Build the Spin binary:<br />
sudo apt-get install -y build-essential byacc flex graphviz<br />
cd $INSTALL_DIR/Spin-version-*/Src<br />
make<br />
sudo cp spin /usr/bin/<br />
#

This is how you can execute a simple model written in Promela, the modeling language for Spin, from the command line:<br />
spin $INSTALL_DIR/Spin-version-*/Examples/hello.pml<br />

The usage of iSpin requires the installation of tk, a graphical user interface toolkit:<br />
sudo apt-get install -y tk<br />
cd $INSTALL_DIR/Spin-version-*/optional_gui/<br />
./ispin.tcl<br />
