![image](https://github.com/molla202/Quai/assets/91562185/4c9ece27-edce-4255-b71b-1a66154a2332)  ,![a8d18948a380bb2184b1b4b098fa61d2_w200](https://github.com/molla202/Quai/assets/91562185/440daf8b-e760-4fb7-9e16-7d02178b2c3c)


## 🚧 Sistem Gereksinimleri
| Bileşenler | Minimum Gereksinimler | 
| ------------ | ------------ |
| CPU |	4|
| RAM	| 8+ GB |
| Storage	| 1TB diola 400gb diyelim |

👉 `Faucet` : https://faucet.quai.network/    Bize platform testleri için laızm olucaktır...

### 🚧 Update ve gereklilikler
```
sudo apt update && sudo apt upgrade -y
sudo apt install curl git wget htop tmux build-essential jq make lz4 gcc unzip -y
```
### 🚧 Go kurulumu
```
sudo rm -rf /usr/local/go
curl -Ls https://go.dev/dl/go1.21.1.linux-amd64.tar.gz | sudo tar -xzf - -C /usr/local
eval $(echo 'export PATH=$PATH:/usr/local/go/bin' | sudo tee /etc/profile.d/golang.sh)
eval $(echo 'export PATH=$PATH:$HOME/go/bin' | tee -a $HOME/.profile)
```
### 👑 Dosyaları çekelim
```
git clone https://github.com/dominant-strategies/go-quai
cd go-quai
```
```
git checkout v1.2.3-rc.4
```
```
cp network.env.dist network.env
```
```
nano network.env
```
👉 Not: içersinde zone bölgeleri var. bunlar bolgesel nodeları ve alt nodeları hespi için yada çalıştıracağım bölge için cüzdan açmamız gerek. yukarıdaki kod ile cüzdan adreslerini bölgeye göre değiştiriyoruz...

![image](https://github.com/molla202/Quai/assets/91562185/6b6807bc-4922-4a0a-b389-c6e0244dbd51)

* SLICES= burda tum bölgeler var. istenilen bölgeler bırakılıp kalan kısım silinecek...

![image](https://github.com/molla202/Quai/assets/91562185/16b09b2d-3094-44ea-a0ff-385ba4e75bbc)

* En alt kısma gelıyoruz ve `EXT_IP=`  ekliyoruz sunucu ipsini yazıyoruz ve `ENABLE_NAT=true` kısmını true yapıyoruz.
 
![image](https://github.com/molla202/Quai/assets/91562185/55c2c669-f63b-4df7-b7f1-f46cbc1b221a)

* Şimdi kuralım...
```
make go-quai
```
* ✔️ Çalıştıralım.. ve `eşleşmesini` bekleyelim. unutmayun run demek için dosyanın içinde olmalıyız mutlaka `cd go-quai`
```
make run
```
👉 Not: Durdurman istiyorsanız make stop yazmanız gerekiyor. gerekli ise. cd go-quai içersinde olduğunuzdan emin olun.
* Loglara bakamak için

👉 Global node çalıştırıyorsanız yada bölgesel bu ana log gösteren komut `tail -f nodelogs/prime.log`

![image](https://github.com/molla202/Quai/assets/91562185/8ebbab6c-3c40-479e-96ed-7c0fe7c38ea3)

👉 Bölgesel görmek için `tail -f nodelogs/region-2.log`

👉 Bölgesel alt zone görmek için `tail -f nodelogs/zone-0-0.log`

👉 Bu kod blokların yüklendiğini gösterıor `tail -f nodelogs/* | grep Appended`

![image](https://github.com/molla202/Quai/assets/91562185/d81a5a22-0264-44a6-a575-1cf167b4704b)

👉 Zone Yüklenen blokları gösterir `tail -f nodelogs/zone-1-0.log | grep Appended`

* 🏆 Eşleşme bitti loglar tamam diyelim. explorer dan kontrolumuzu yapalım. madencilik yapacağımız zone bölgesinden cüzdanımızı olusturup ekledik tamam. şimdi diğer sayfaya stratum kurulumuna geçelim aynı sunucu üzerine node"un yanına kurulacak
https://paxos2.colosseum.quaiscan.io/     explorerimiz burası yukarıdan bölge ve zone göre bakabilirsiniz...

![image](https://github.com/molla202/Quai/assets/91562185/09776fc6-2b94-4b2a-961a-3d1dbe1bb738)


👉 NOT: alt kısım ağ çalışmaya başlayınca update gelirse yada baştan kurmak zorundaysanız.. üst kısımla alakalı değildir.
* Güncelleme geldiğinde ve ağ çalıştığında sürüm numarası değişecek ve kurulumu yapacağız. alttaki kod kurulumu silmek günncelemyi yapmak içindir. `cd go-quai` dosyanın içinde olduğunuzdan emin olun.

`run make stop && rm -rf nodelogs && rm -rf ~/.quai && git checkout v0.17.0-rc.3 && cp network.env.dist network.env`  ardından nano network.env düzenlemeleri yapıp `make run` diyoruz ve başlatıyoruz.
