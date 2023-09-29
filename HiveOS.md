![image](https://github.com/molla202/Quai/assets/91562185/4c9ece27-edce-4255-b71b-1a66154a2332)  ,![a8d18948a380bb2184b1b4b098fa61d2_w200](https://github.com/molla202/Quai/assets/91562185/440daf8b-e760-4fb7-9e16-7d02178b2c3c)

`UYARI` : Bu iş biraz profesyonellik ve bilgi gerektirir. hiç anlamıyorsanız ya daha önce yapan birinden yardım alın yada aldığınız risklerin farkında olun. madencilik ciddi bir iştir kartınıza zarar verebilirsiniz. 

# HİVEOS KURULUMU
- Daha önce hiveos kullanmadıysanız. kısaca linux tabanlı bir madenci yazılımıdır. imaj dosyasını indirip harici hdd falshbellek içine atıp bundan boot edıyoruz. işlemi yapınca tüm veriler silinir cihazda yani imaj yazacağımız disk yada flashbellekte verilerin yedeğini alın yada silinmesinde sakınca yoksa başlayın. minimum 8gb civarı bir flash bellek yeterlidir..
- bir ekran akrtınız var bunu bir şekilde bir pcye takmamız lazım ama unutmayın ekran akrtını kaldırıcak bir güç kaynağı olmalı
- https://download.hiveos.farm/latest/  Adresinden imakı indirelim...
- [BURADAN](https://github.com/pbatard/rufus/releases/download/v4.2/rufus-4.2p.exe) rufusu indirelim açalım ve imajı gösterip flashbellek seçip yazalım...
- [BURADAN](https://id.hiveon.com/auth/realms/id/protocol/openid-connect/auth?client_id=account&response_type=code&scope=email&redirect_uri=https%3A%2F%2Fthe.hiveos.farm&ui_locales=en) register kısmından üuye olup bağlanın
- daha sonrasını yazarak anlatmam birşey ifade etmeyecek youtube üzerinden hiveos kurulumu yazarsanız video içerikleri var kısaca farm kurup altına bölüm oluşturuyoruz. daha sonra bu alt kısma girince ayarlar bölümünden bir metin belhesi indirmemiz gerekiyor ayarların ve bağlantılar için bilgilerin olduğu bunu flash belleğe kopyalıyoruz. daha sonra madencilik cihazınıza takıp açın otomatik başlayacaktır bu cihaza bir ekran takmanıza mause klavye takmanıza dahi gerek yok tek yapacağınız enerji kablosu ve internet kablosunu bağlamak...
- açıldıktan 5 dakika sürmeden hiveos platformundna online olacaktır.
- daha sonra yukarıdan hiveshell tıklayıp açılan sayfada aşağıdaki adımları yapacağız... hiveosda ekran kartının ayarlarını yapmak gerekir. önerilen ayarlardan kartınız için progpow ayarlarını görebilirsiniz popular...

- Sağ üste + işaretinden yeni farm ekleyebilirsiniz..

![image](https://github.com/molla202/Quai/assets/91562185/d8333d56-9032-42d7-9f89-e35d1ca51af8)

- farmı oluşturduktan sonra  worker olusturuyoruz sağ ustten yine

![image](https://github.com/molla202/Quai/assets/91562185/e1537fa8-9345-41cd-8026-12c514f7b2d1)

- daha sonra config dosyasını indirip flash belleğe atıyoruz. resmin sağ altında burda bilgiler var tam ekran atamadım ama siz biraz üst sağda göruceksınız.

![image](https://github.com/molla202/Quai/assets/91562185/fd8213a1-a3f8-45be-ba5b-24002c0eb0e5)

- flashı taktık cihazı açtık ve online olmasını beklıyoruz. yukarıda yazıyor online olunca arada olmadı sayfayı yenılersınız.

![image](https://github.com/molla202/Quai/assets/91562185/9c8804eb-62d6-4735-860b-30ea1d670c15)

- kart ayarı kartınız gorundukten sonra sağdaki ibreye tıklayınız. açılan sayfadan ayar yapılıyor popular kısmından algo kısmından progpow bakarak insanalrın kullandığı ayarları görebilirsiniz kartınızdan ancak yoksa internetten araştırınız. mesela hangi coinler bu algoyu kullanıyor gibi onlar üzerinden bir ayar tutturmak lazım ful güçte çalıştırmak kart için sağlıklı değildir... en kötü eth algosunda ayarlayıp yada ravende ayarlayıp deneyiniz...

![image](https://github.com/molla202/Quai/assets/91562185/b18f33af-a6b1-459d-a0e2-45cb37e8b9d5)

![image](https://github.com/molla202/Quai/assets/91562185/9b74b9be-f527-4abe-b08d-7303ec32e5f8)


- şimdi paneli açalım ve alttaki işlemleri yapalım. remote acces yazan kare >_ amblemli zımpırtı :D

![image](https://github.com/molla202/Quai/assets/91562185/be50ffa9-e4b1-4a15-a63e-216fd56af28e)


NOT: başlamadna önce mutlaka bol bol video izleyin hiveos madenciliği hakkında.





-----------
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





