view video card specifications
lspci -v | less

Amd control panel
sudo amdcccle


steps

1 sudo apt-get update && sudo apt-get upgrade

2 install chrome
wget https://dl.google.com/linux/direct/google-chrome-stable_current_amd64.deb

3 install amd-catalyst
wget http://www2.ati.com/drivers/linux/amd-driver-installer-catalyst-13-4-linux-x86.x86_64.zip
cp ~/Downloads/amd-driver-installer-catalyst-13-4-x86.x86_64.run
chmod +x amd-driver-installer-catalyst-13-4-x86.x86_64.run
./amd-driver-installer-catalyst-13-4-x86.x86_64.run

4 copy 20_custom-ehci_hcd to /etc/pm/sleep.d
sudo cp 20_custom-ehci_hcd /etc/pm/sleep.d/

5 install samsung tools
sudo add-apt-repository ppa:voria/ppa
sudo apt-get update && sudo apt-get upgrade
sudo apt-get install samsung-tools samsung-laptop

6 install gpointing device settings
sudo apt-get install gpointing-device-settings
config device settings

7 track pad right click (optional)
sudo add-apt-repository ppa:chasedouglas/clickpad
sudo apt-get update && sudo apt-get dist-upgrade

use xinput to find touchpad and find a line like this
->  ETPS/2 Elantech Touchpad id=12	[slave  pointer  (2)]"

wget "http://www.colar.net/enable-clickpad.sh"
chmod +x enable-clickpad.sh
wget "http://www.colar.net/enable-rightbutton.sh"
chmod +x enable-rightbutton.sh

gedit ~/.gnomerc
~/enable-clickpad.sh 12 
~/enable-rightbutton.sh 12

8 fix dual-screen issues
sudo sh -c 'echo N > /sys/module/drm_kms_helper/parameters/poll'

make that permantent
sudo sh -c 'echo "options drm_kms_helper poll=0" >> /etc/modprobe.d/local.conf'
sudo update-initramfs -u

9 install oracle jdk
sudo add-apt-repository ppa:webupd8team/java
sudo apt-get update
sudo apt-get install oracle-java7-installer

10 install vim
sudo apt-get install vim
mkdir ~/.vim/bundle

11 install vundle
git clone https://github.com/gmarik/vundle.git ~/.vim/bundle/vundle

12 install build essential
sudo apt-get install build-essential

13 install curl
sudo apt-get install curl

14 install rvm
curl -L https://get.rvm.io | bash
rvm requirements

15 install postgresql
sudo apt-get install postgresql-9.1
sudo apt-get install libpq-dev
copy pg_hba.conf to /etc/postgresql/9.1/main/

install mysql
sudo apt-get install mysql-server-5.5
sudo apt-get install libmysql-ruby libmysqlclient-dev

* install imagemagick
sudo apt-get install imagemagick

* update fstab file for fast specs
open /etc/fstab
change
UUID=f54ae48f-7525-4b18-92bf-dbe5b1fb9be6 / ext4 errors=remount-ro 0 1
to
UUID=f54ae48f-7525-4b18-92bf-dbe5b1fb9be6 / ext4 barrier=0,errors=remount-ro 0 1

* install pixel ruler
sudo apt-get install screen ruler

* install lib extension for capybara
sudo apt-get install libqt4-dev

* install vagrant
http://files.vagrantup.com/packages/7e400d00a3c5a0fdf2809c8b5001a035415a607b/vagrant_1.2.2_x86_64.deb

* install virtual box
sudo apt-get install virtualbox

* install the silver searcher
http://swiftsignal.com/packages/ubuntu/precise/the-silver-searcher_0.14-1_amd64.deb

* install redis server
sudo apt-get install redis-server

*install LPprof
