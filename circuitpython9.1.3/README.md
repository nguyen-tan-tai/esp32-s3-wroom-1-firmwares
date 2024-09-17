https://learn.adafruit.com/building-circuitpython/espressif-build
https://learn.adafruit.com/building-circuitpython/build-circuitpython


apt update -y
apt install ninja-build cmake -y
apt install git -y
apt install python3 -y
apt install python3-pip -y
apt install python-is-python3 -y
apt install libusb-1.0-0-dev -y
pip install minify_html
pip install jsmin

git clone https://github.com/adafruit/circuitpython.git
cd /workspace/circuitpython
git checkout 8.2.6
pip install --upgrade -r requirements-dev.txt
pip install --upgrade -r requirements-doc.txt

cd /workspace/circuitpython/ports/espressif
make fetch-port-submodules

cd /workspace/circuitpython/ports/espressif
./esp-idf/install.sh
. ./esp-idf/export.sh


make V=2 -j8 BOARD=ESP32-S3-WROOM-1-N4 
