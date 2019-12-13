Para Bozma Makinesi

Büþra Erkan - 170201018
Gözde Örgü  - 170201005

Bu readme.txt dosyasý, En Az Sayýda Bozuk Para Verme Projesi'ne aittir.
Bu paket, kaynak kodu ile ayný dizin içerisinde bulunacaktýr.


1-PAKETÝN ÝÇERÝÐÝ:
----------
170201018-170201005.txt -Projenin tek dosyaya indirgenmiþ salt kaynak kodu.
readme.txt - Bu dosya.
170201018-170201005.zip - Projenin kaynak kodunun ve yardýmcý dosyalarýn ziplenmiþ hali.
rapor.doc - Proje raporu- Projenin tek dosyaya indirgenmiþ salt kaynak kodu.
readme.txt - Bu dosya.
----------


2-SÝSTEM GEREKSÝNÝMLERÝ:
-------------------
Oracle VM virtualbox - https://www.virtualbox.org/
Sanal Makine Ýmajý   - https://github.com/KOU-Embedded-System-Lab/os-base-image/releases
-------------------


3-PROJEYÝ ÇALIÞTIRMAK:
-------------------
Paket içeriðini yukarýda görebilirsiniz.

Bu kod, 2 adet önceden tanýmlanmýþ sanal makinelerde çalýþtýrýldý.

Sanal makineyi indirmek için;
https://github.com/KOU-Embedded-System-Lab/os-base-image/releases
adresini ziyaret edebilirsiniz.

Bu iki durumda da, kod, herhangi bir hata vermeksizin, daha önceden
belirlenen kriterlere uygun çalýþtý.


4-KODU DERLEMEK:
------------------
Artýk bilgisayarýmýzda kurulu olan sanal makine ile kodu kolayca derleyebiliriz.

Projeyi geliþtirim kartýnda çalýþtýrmak için kodu daha önceden oluþturulmuþ Tiva C
projesinde yer alan "main.c"ye yapýþtýrýp build butonuna týkladýktan sonra debug 
butonuna týklamanýz yeterli.

Eðer kart, sanal makine tarafýndan bulunamadýysa (OpenOCD hatasý) sanal makineye
baðlý olan bir kart olmayabilir. Sað alt kýsýmdan usb ikonuna sað týklayarak 
Texas Instruments'ý seçip sanal makineye baðlamanýz gerekmektedir.

Ana Makinesi GNU/Linux olan makinelerde VirtualBox, kullanýcý izinlerine sahip
olmayabiliyor. Eðer takýlý olan USB aygýtlarý tanýmýyorsa, 
'sudo usermod -G vboxusers -a $USER'
kodunu çalýþtýrmanýz ve sisteminizi yeniden baþlatmanýz gerekmektedir. 
------------------


5- PARAMETRELER
---------------------------
Kodun çalýþmasý için baþlangýçta herhangi bir parametre gerekmiyor.
------------------


6- PROGRAMIN KULLANIMI
-----------------------------
Bu proje kullanýcýdan aldýðý parayý, ürüne göre deðerlendirip kullanýcýya
verilen para üstünün en az sayýda bozuk paradan oluþmasýný amaçlar.

Öncelikle kullanýcýnýn otomata para girmesi gerekmektedir. Bu iþlem 
butonlarla saðlanmaktadýr. Ýlk dört buton para giriþi içindir. Ýlk buton 1 TL,
ikinci buton 50 Kuruþ, üçüncü buton 25 Kuruþ içindir. Dördüncü buton ise
para atma iþleminin bittiðini belirten "Bitiþ" butonudur. Örneðin kullanýcý
birinci butona 2 kere, ikinci butona 3 kere ve üçüncü butona 1 kere basarsa
otomata 3 TL 25 Kuruþ para giriþinde bulunacaktýr.

Sýradaki iþlem ürün seçme iþlemidir. Otomatta toplamda 5 çeþit ürün 
bulunmaktadýr. Bunlar su, çay, kahve, çikolata ve bisküvidir. Beþinci
buton su, altýncý buton çay, yedinci buton kahve, sekizinci buton çikolata,
dokuzuncu buton bisküvi için kullanýlmaktadýr. Onuncu buton "Bitiþ" butonudur.
Kullanýcý hangi üründen kaç tane istiyorsa önce ilgili butona adet sayýsý kadar
basmalý daha sonra da "Bitiþ" butonuna basmalýdýr.Kullanýcý eðer "Reset" butonuna
basarsa bütün iþlemler iptal olur. "Reset" butonu on birinci butondur.

Tüm bu iþlemlerden sonra program 1-4 (1 ve 4 dahil) arasýnda random sayý
üretilir. Eðer random sayý 2 olursa para sýkýþma olur  Para sýkýþma iþleminde 
kýrmýzý led yanar aksi durumda (random üretilen sayý 2 e eþit deðilse) problem 
olmadýðýný belirten yeþil led yanar Para sýkýþma durumunda kiþiye para iadesi 
yapýlacak ve tuþlanan ürünler stoktan düþmez. Tüm bu kontrollerden sonra 
Reset butonuna basýlýr. 

Son olarak kullanýcýya para üstü verilir.  Otomat kasada bulunan bozuk 
paralardan en azýný kullanarak kullanýcýya bozuk para verir. Kasa sürekli kontrol ve
güncelleme yapar. Eðer kasada yeteri kadar para yoksa "Kasada yeterli para yoktur"
uyarýsý verilir.

 




