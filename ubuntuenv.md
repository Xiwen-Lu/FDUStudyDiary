
# install xrdp so that it can visit from local windows
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

generate the ssh key in the computer
ssh-keygen-t rsa
copy the /home/your_username/.ssh/id_rsa.pub to git repository's keys field
** git remote set-url origin git@github.com:username/your-repository.git

git commit -a -m "message"

# xhost
when i try to run Matlab install on user:root, it failed.
the reason is that: you can't log in as one user, and try to run something as another user within that users session ..

the solution: Just to put this on this thread, here you go: Run this command first (while you are logged in as the normal user):

xhost +local:root

or this will allow access by any user on that physical computer:

xhost +localhost

That allows root/others to have access to the x server. See the man pages for xhost. This, however is only effective for that session, so if you always want root access, then you need to put this in a startup script.

# input piniyin sougou
sudo apt-get install fcitx
sudo dpkg -i sogoupinyin_..._.deb

# docker
sudo apt install docker.io
create multiple terminal with one image:
one: docker run -it container_name
twO: docker exec -it container_name bash

save the change of container to a new image
sudo docker ps -l
sudo dockek commit xxx "new_imagename"

copy the docker container file to the dest pc
sudo docker cp containerid:filepath filepath

to get the dest pc root privilege
run with '--privileged'

`docker ps` to see all the running containers

## create a cuda docker container

# add a docker group
sudo groupadd docker
sudo usermod -aG docker $USER

# some usage about the ubuntu system
`ps aux` to see the pid in system
`kill -9 pid` to kill some pid

# dot graph view
sudo apt-get install graphviz graphviz-doc
dot -Tpng test.dot -o test.png
dot -Tsvg test.dot -o test.svg
dot test.dot -Tpdf -o test.pdf

# generate the dot of network in python, visualize the deeplearning network
from torchviz import make_dot
y = model(input)
g = make_dot(y)
g.render('name', view = False)

# install TexStudio on ubuntu
because texstudio isnot in the public repository of ubuntu, so we must add is ppa on the ubuntu repository
$ sudo add-apt-repository ppa:sunderme/texstudio
$ sudo apt remove texstudio-doc texstudio-l10n
$ sudo apt update
$ sudo apt install texstudio
$ sudo apt remove --autoremove texstudio

# delete a swap file
rm ...swp

# install docker wechat on ubuntu
Method1:
install docker-wehcat:dochat
wget https://raw.githubusercontent.com/huan/docker-wechat/master/dochat.sh

xhost +; sudo chown -R $USER $HOME/DoChat/
sudo chown -R $(whoami) $HOME/DoChat/

fail to install wechat, because it always remind me that disabling to patch something

# zotero
download the tar.gz
create a desktop: 
run the set_launch_icon 
then, ln -s zotero.desktop ~/.local/share/applications/zotero.desktop
attention, here the source file zotero.desktop should use the absolute filepath, cannnot use the relevant path. 

# tex-live, and let it can automatically install packages
sudo apt-get install texlive-full

# install wine
search for wineHQ (wine linux), then follow the instruction of the website

# fix the apt-get update problem
sudo sed -i.bak 's/id.old-/old-/g' /etc/apt/sources.list
sudo apt-get update

another problem about PPA, the solution is to delete the PPA in the software&update.

# uninstall software
sudo apt list --installed
sudo apt remove package-name

# wechat
deepin wechat
first need to install the deepin wine

# error while loading shared libraries: libtinfo.so.5: No such file or directory
sudo apt-get install libtinfo5

# clash for windows
just download the clash for windows ubuntu, that's fine.

# kill application in ubuntu
Alt+F2, and press xkill
or, open the system monitor, kill the process

# find the unresolved library
in Qt
export QT_DEBUG_PLUGINS=1
find the true reason that cause the problem, such as 'libqxcb.so' cannot import
then, cd the directory of 'libqxcb.so'
run 'ldd libqxcb.so'
then find something that not found, such as 'libxcb-cursor.so.0'
then install it by 'sudo apt-get install libxcb-cursor0'
Ok, then the problem solved.


# edit the swap running system
sudo gedit /etc/sysctl.conf
# add at last
vm.swappiness=20


# to uninstall something
first can find it by see the application in /usr/share/applications or ~/.local/share/applications
then find the path of the software.
