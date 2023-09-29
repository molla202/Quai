
![image](https://github.com/molla202/Quai/assets/91562185/4c9ece27-edce-4255-b71b-1a66154a2332)  ,![a8d18948a380bb2184b1b4b098fa61d2_w200](https://github.com/molla202/Quai/assets/91562185/440daf8b-e760-4fb7-9e16-7d02178b2c3c)



### Update ve gereklilikler
```
sudo apt update && sudo apt upgrade -y
sudo apt install -y git make cmake build-essential mesa-common-dev
```
-----
Not: Nvidia kartınız varsa altakinden driver kurabilirsiniz
```
sudo apt install -y nvidia-driver-535
```
----
```
sudo reboot
```

----------
Not: Eğer amd ekran kartı üst düzey kullanıyorsanız. altaki driverı kurmanız gerekebilir ancak lütfen önce bu kısmı atlayın madenci çalışmas ise deneyiniz...
```
sudo apt update && sudo apt upgrade -y && sudo apt autoremove -y
sudo apt install -y wget
```
```
wget https://repo.radeon.com/amdgpu-install/23.20/ubuntu/focal/amdgpu-install_5.7.50700-1_all.deb
```
```
udo dpkg -i amdgpu-install_5.7.50700-1_all.deb
```
```
sudo amdgpu-install --usecase=workstation -y --vulkan=pro --opencl=rocr
```
```
sudo usermod -a -G render $LOGNAME
sudo usermod -a -G video $LOGNAME
```
```
sudo reboot
```

--------------------


### Dosyaları çekelim...
```
git clone https://github.com/dominant-strategies/quai-gpu-miner && cd quai-gpu-miner
```
```
git submodule update --init --recursive
```
### Dosyayı oluşturalım...
Not: oluşturması zaman alıcaktır uzun sürebilir bekleyiniz...
```
mkdir build && cd build
```
### Madenciyi başlatalım...
Not: Standart stratum portu 3333 tür. node ve stratum çalışan sunucunuzun ipsini yazacaksınız. eğer bir linux ubuntu kullanıyor ve ekrankartı bağlı pcnizde 3nüde birden çalıştıracaksanız. local ipnizide yazabilirsiniz.
```
./ethcoreminer/ethcoreminer -G -P stratum://PROXYIPADRESS:STRATUMPORT
```

--------------------------









