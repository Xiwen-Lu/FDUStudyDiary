sudo passwd root

sudo apt install xrdp
sudo systemctl enable --now xrdp
sudo ufw allow from any to any port 3389 proto tcp

sudo vim /etc/xrdp/startwm.sh


unset DBUS_SESSION_BUS_ADDRESS
unset XDG_RUNTIME_DIR
. $HOME/.profile


# install cuda11.1 and cudnn8.2 and pytorch on RTX3090 with Ubuntu18.04 LTS
Driver Version 470.63.01
CUDA Version 11.4
cuDNN 8.2.1

make sure PATH includes /usr/local/cuda-11.1/bin
LD_LIBRARY_PATH includes /usr/local/cuda-11.1/lib64

export PATH=/usr/local/cuda-10.2/bin${PATH:+:${PATH}}
export LD_LIBRARY_PATH=/usr/local/cuda-10.2/lib64${LD_LIBRARY_PATH:+:${LD_LIBRARY_PATH}}

download cuDNN Library for Linux

tar -xzvf ...

Copy the following files into the CUDA Toolkit directory, and change the file permissions.
$ sudo cp cuda/include/* /usr/local/cuda/include/
$ sudo cp cuda/lib64/*/usr/local/cuda/lib64/
$ sudo chmod a+r /usr/local/cuda/include/cudnn.h /usr/local/cuda/lib64/libcudnn*

like usual, use alacarte to edit my Menu.
sudo apt-get install alacarte

# git 
set git token
username:(git username)
password:(git token)
git status


