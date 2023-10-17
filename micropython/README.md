apt update -y
apt install ninja-build cmake -y
apt install git -y
apt install python3-pip -y
apt install python-is-python3 -y


cd circuitpython/ports/espressif
esp-idf/install.sh

git clone https://github.com/adafruit/circuitpython.git
git checkout 8.2.6

pip3 install --upgrade -r requirements-dev.txt
pip3 install --upgrade -r requirements-doc.txt


cd circuitpython/ports/espressif
esp-idf/install.sh

apt install libusb-1.0-0-dev -y
. ./esp-idf/export.sh



pip3 install minify_html
pip3 install jsmin

make V=2 BOARD=esp32-s3-wroom-1-n4 
