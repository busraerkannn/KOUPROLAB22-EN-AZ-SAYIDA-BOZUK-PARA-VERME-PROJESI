En Az Sayıda Bozuk Para Verme

Büşra Erkan - 170201018
Gözde Örgü  - 170201005

Bu readme.txt dosyası, En Az Sayıda Bozuk Para Verme Projesi'ne aittir.
Bu paket, kaynak kodu ile aynı dizin içerisinde bulunacaktır.


1-PAKETİN İÇERİĞİ:
----------
170201018-170201005.txt -Projenin tek dosyaya indirgenmiş salt kaynak kodu.
readme.txt - Bu dosya.
170201018-170201005.zip - Projenin kaynak kodunun ve yardımcı dosyaların ziplenmiş hali.
rapor.doc - Proje raporu- Projenin tek dosyaya indirgenmiş salt kaynak kodu.
readme.txt - Bu dosya.
----------


2-SİSTEM GEREKSİNİMLERİ:
-------------------
Oracle VM virtualbox - https://www.virtualbox.org/
Sanal Makine İmajı   - https://github.com/KOU-Embedded-System-Lab/os-base-image/releases
-------------------


3-PROJEYİ ÇALIŞTIRMAK:
-------------------
Paket içeriğini yukarıda görebilirsiniz.

Bu kod, 2 adet önceden tanımlanmış sanal makinelerde çalıştırıldı.

Sanal makineyi indirmek için;
https://github.com/KOU-Embedded-System-Lab/os-base-image/releases
adresini ziyaret edebilirsiniz.

Bu iki durumda da, kod, herhangi bir hata vermeksizin, daha önceden
belirlenen kriterlere uygun çalıştı.


4-KODU DERLEMEK:
------------------
Artık bilgisayarımızda kurulu olan sanal makine ile kodu kolayca derleyebiliriz.

Projeyi geliştirim kartında çalıştırmak için kodu daha önceden oluşturulmuş Tiva C
projesinde yer alan "main.c"ye yapıştırıp build butonuna tıkladıktan sonra debug 
butonuna tıklamanız yeterli.

Eğer kart, sanal makine tarafından bulunamadıysa (OpenOCD hatası) sanal makineye
bağlı olan bir kart olmayabilir. Sağ alt kısımdan usb ikonuna sağ tıklayarak 
Texas Instruments'ı seçip sanal makineye bağlamanız gerekmektedir.

Ana Makinesi GNU/Linux olan makinelerde VirtualBox, kullanıcı izinlerine sahip
olmayabiliyor. Eğer takılı olan USB aygıtları tanımıyorsa, 
'sudo usermod -G vboxusers -a $USER'
kodunu çalıştırmanız ve sisteminizi yeniden başlatmanız gerekmektedir. 
------------------


5- PARAMETRELER
---------------------------
Kodun çalışması için başlangıçta herhangi bir parametre gerekmiyor.
------------------


6- PROGRAMIN KULLANIMI
-----------------------------
Bu proje kullanıcıdan aldığı parayı, ürüne göre değerlendirip kullanıcıya
verilen para üstünün en az sayıda bozuk paradan oluşmasını amaçlar.

Öncelikle kullanıcının otomata para girmesi gerekmektedir. Bu işlem 
butonlarla sağlanmaktadır. İlk dört buton para girişi içindir. İlk buton 1 TL,
ikinci buton 50 Kuruş, üçüncü buton 25 Kuruş içindir. Dördüncü buton ise
para atma işleminin bittiğini belirten "Bitiş" butonudur. Örneğin kullanıcı
birinci butona 2 kere, ikinci butona 3 kere ve üçüncü butona 1 kere basarsa
otomata 3 TL 25 Kuruş para girişinde bulunacaktır.

Sıradaki işlem ürün seçme işlemidir. Otomatta toplamda 5 çeşit ürün 
bulunmaktadır. Bunlar su, çay, kahve, çikolata ve bisküvidir. Beşinci
buton su, altıncı buton çay, yedinci buton kahve, sekizinci buton çikolata,
dokuzuncu buton bisküvi için kullanılmaktadır. Onuncu buton "Bitiş" butonudur.
Kullanıcı hangi üründen kaç tane istiyorsa önce ilgili butona adet sayısı kadar
basmalı daha sonra da "Bitiş" butonuna basmalıdır.Kullanıcı eğer "Reset" butonuna
basarsa bütün işlemler iptal olur. "Reset" butonu on birinci butondur.

Tüm bu işlemlerden sonra program 1-4 (1 ve 4 dahil) arasında random sayı
üretilir. Eğer random sayı 2 olursa para sıkışma olur  Para sıkışma işleminde 
kırmızı led yanar aksi durumda (random üretilen sayı 2 e eşit değilse) problem 
olmadığını belirten yeşil led yanar Para sıkışma durumunda kişiye para iadesi 
yapılacak ve tuşlanan ürünler stoktan düşmez. Tüm bu kontrollerden sonra 
Reset butonuna basılır. 

Son olarak kullanıcıya para üstü verilir.  Otomat kasada bulunan bozuk 
paralardan en azını kullanarak kullanıcıya bozuk para verir. Kasa sürekli kontrol ve
güncelleme yapar. Eğer kasada yeteri kadar para yoksa "Kasada yeterli para yoktur"
uyarısı verilir.

 




