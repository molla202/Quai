
![image](https://github.com/molla202/Quai/assets/91562185/4c9ece27-edce-4255-b71b-1a66154a2332)  ,![a8d18948a380bb2184b1b4b098fa61d2_w200](https://github.com/molla202/Quai/assets/91562185/440daf8b-e760-4fb7-9e16-7d02178b2c3c)

#### Açıklama

- Node kurulumundan sonra bu kısım zor deil.
- madencilik yapacağınız bölgeyi seçiyorsunuz. ve o bölgede cüzdan olusturuyorsunuz zaten. altta o bölgenin kodunu çalıştırdığınızda çalışacaktır.
- harici bir ayar yok.
- Bir Age Of Empire atasözü derki : Madenci kazarım

### Dosyaları çekelim
```
cd
git clone https://github.com/dominant-strategies/go-quai-stratum
cd go-quai-stratum
```
```
git checkout v01.2.3-rc.4
```
```
cp config/config.example.json config/config.json
```
```
make quai-stratum
```
### Çalıştıralım
Not: seçeceğimiz bölgeyi ayarlamamız lazım.
```
./build/bin/quai-stratum --region=REGION-WS-PORT --zone=ZONE-WS-PORT
```
![image](https://github.com/molla202/Quai/assets/91562185/8c09fa7c-5338-4333-b5b2-54c761751352)


| Chain name | Chain index |  Command |
| ------------ | ------------ | ------------ |
| Cyprus-1 | [0 0]	| `./build/bin/quai-stratum --region=8579 --zone=8611` |
| Cyprus-2 | [0 1]	| `./build/bin/quai-stratum --region=8579 --zone=8643` |
| Cyprus-3 | [0 2]	| `./build/bin/quai-stratum --region=8579 --zone=8675` |
| Paxos-1 | [1 0]	| `./build/bin/quai-stratum --region=8581 --zone=8613` |
| Paxos-2 | [1 1]	| `./build/bin/quai-stratum --region=8581 --zone=8645` |
| Paxos-3 | [1 2]	| `./build/bin/quai-stratum --region=8581 --zone=8677` |
| Hydra-1 | [2 0]	| `./build/bin/quai-stratum --region=8583 --zone=8615` |
| Hydra-2 | [2 1]	| `./build/bin/quai-stratum --region=8583 --zone=8647` |
| Hydra-3 | [2 2]	| `./build/bin/quai-stratum --region=8583 --zone=8679` |


![image](https://github.com/molla202/Quai/assets/91562185/c7ec2397-ce06-45a8-9c1a-e089b0846993)





```./build/bin/quai-stratum --region=8579 --zone=8611```
