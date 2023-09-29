![image](https://github.com/molla202/Quai/assets/91562185/4c9ece27-edce-4255-b71b-1a66154a2332)  ,![a8d18948a380bb2184b1b4b098fa61d2_w200](https://github.com/molla202/Quai/assets/91562185/440daf8b-e760-4fb7-9e16-7d02178b2c3c)



### Update ve gereklilikler
```
sudo apt update && sudo apt upgrade -y
sudo apt install -y git cmake build-essential mesa-common-dev
```
### Amd sürücüsünü güncellemek isterseniz
```
sudo amd-ocl-install 22.20
```
### Nvidia sürücüsünü güncellemek isterseniz
```
sudo nvidia-driver-update
```
- Daha sonra bi reset atalım hiveosa
```
sreboot
```


### Dosyaları çekelim
```
git clone https://github.com/dominant-strategies/quai-gpu-miner && cd quai-gpu-miner
```
```
git submodule update --init --recursive
```
```
mkdir build && cd build
```
- Altaki kod uzun sürer
```
cmake .. && cmake --build .
```

### Madenci çalıştırma
```
./ethcoreminer/ethcoreminer -G -P stratum://PROXYIPADRESS:STRATUMPORT
```





