Para Bozma Makinesi

B��ra Erkan - 170201018
G�zde �rg�  - 170201005

Bu readme.txt dosyas�, En Az Say�da Bozuk Para Verme Projesi'ne aittir.
Bu paket, kaynak kodu ile ayn� dizin i�erisinde bulunacakt�r.


1-PAKET�N ��ER���:
----------
170201018-170201005.txt -Projenin tek dosyaya indirgenmi� salt kaynak kodu.
readme.txt - Bu dosya.
170201018-170201005.zip - Projenin kaynak kodunun ve yard�mc� dosyalar�n ziplenmi� hali.
rapor.doc - Proje raporu- Projenin tek dosyaya indirgenmi� salt kaynak kodu.
readme.txt - Bu dosya.
----------


2-S�STEM GEREKS�N�MLER�:
-------------------
Oracle VM virtualbox - https://www.virtualbox.org/
Sanal Makine �maj�   - https://github.com/KOU-Embedded-System-Lab/os-base-image/releases
-------------------


3-PROJEY� �ALI�TIRMAK:
-------------------
Paket i�eri�ini yukar�da g�rebilirsiniz.

Bu kod, 2 adet �nceden tan�mlanm�� sanal makinelerde �al��t�r�ld�.

Sanal makineyi indirmek i�in;
https://github.com/KOU-Embedded-System-Lab/os-base-image/releases
adresini ziyaret edebilirsiniz.

Bu iki durumda da, kod, herhangi bir hata vermeksizin, daha �nceden
belirlenen kriterlere uygun �al��t�.


4-KODU DERLEMEK:
------------------
Art�k bilgisayar�m�zda kurulu olan sanal makine ile kodu kolayca derleyebiliriz.

Projeyi geli�tirim kart�nda �al��t�rmak i�in kodu daha �nceden olu�turulmu� Tiva C
projesinde yer alan "main.c"ye yap��t�r�p build butonuna t�klad�ktan sonra debug 
butonuna t�klaman�z yeterli.

E�er kart, sanal makine taraf�ndan bulunamad�ysa (OpenOCD hatas�) sanal makineye
ba�l� olan bir kart olmayabilir. Sa� alt k�s�mdan usb ikonuna sa� t�klayarak 
Texas Instruments'� se�ip sanal makineye ba�laman�z gerekmektedir.

Ana Makinesi GNU/Linux olan makinelerde VirtualBox, kullan�c� izinlerine sahip
olmayabiliyor. E�er tak�l� olan USB ayg�tlar� tan�m�yorsa, 
'sudo usermod -G vboxusers -a $USER'
kodunu �al��t�rman�z ve sisteminizi yeniden ba�latman�z gerekmektedir. 
------------------


5- PARAMETRELER
---------------------------
Kodun �al��mas� i�in ba�lang��ta herhangi bir parametre gerekmiyor.
------------------


6- PROGRAMIN KULLANIMI
-----------------------------
Bu proje kullan�c�dan ald��� paray�, �r�ne g�re de�erlendirip kullan�c�ya
verilen para �st�n�n en az say�da bozuk paradan olu�mas�n� ama�lar.

�ncelikle kullan�c�n�n otomata para girmesi gerekmektedir. Bu i�lem 
butonlarla sa�lanmaktad�r. �lk d�rt buton para giri�i i�indir. �lk buton 1 TL,
ikinci buton 50 Kuru�, ���nc� buton 25 Kuru� i�indir. D�rd�nc� buton ise
para atma i�leminin bitti�ini belirten "Biti�" butonudur. �rne�in kullan�c�
birinci butona 2 kere, ikinci butona 3 kere ve ���nc� butona 1 kere basarsa
otomata 3 TL 25 Kuru� para giri�inde bulunacakt�r.

S�radaki i�lem �r�n se�me i�lemidir. Otomatta toplamda 5 �e�it �r�n 
bulunmaktad�r. Bunlar su, �ay, kahve, �ikolata ve bisk�vidir. Be�inci
buton su, alt�nc� buton �ay, yedinci buton kahve, sekizinci buton �ikolata,
dokuzuncu buton bisk�vi i�in kullan�lmaktad�r. Onuncu buton "Biti�" butonudur.
Kullan�c� hangi �r�nden ka� tane istiyorsa �nce ilgili butona adet say�s� kadar
basmal� daha sonra da "Biti�" butonuna basmal�d�r.Kullan�c� e�er "Reset" butonuna
basarsa b�t�n i�lemler iptal olur. "Reset" butonu on birinci butondur.

T�m bu i�lemlerden sonra program 1-4 (1 ve 4 dahil) aras�nda random say�
�retilir. E�er random say� 2 olursa para s�k��ma olur  Para s�k��ma i�leminde 
k�rm�z� led yanar aksi durumda (random �retilen say� 2 e e�it de�ilse) problem 
olmad���n� belirten ye�il led yanar Para s�k��ma durumunda ki�iye para iadesi 
yap�lacak ve tu�lanan �r�nler stoktan d��mez. T�m bu kontrollerden sonra 
Reset butonuna bas�l�r. 

Son olarak kullan�c�ya para �st� verilir.  Otomat kasada bulunan bozuk 
paralardan en az�n� kullanarak kullan�c�ya bozuk para verir. Kasa s�rekli kontrol ve
g�ncelleme yapar. E�er kasada yeteri kadar para yoksa "Kasada yeterli para yoktur"
uyar�s� verilir.

 




