**SORU 1: CRYPTOGRAPHY FUN CLUB** *(TryHackMe)*

*Flag Formatı: THM{}*

**1.1 Flag format: THM{X_X_X_X_X_X_X_X}** 
[Ses dosyası](Sounds/sound-0.wav)

**ÇÖZÜM**

Görev dosyasını indirelim. İndirdiğim ses dosyasından da anlayabileceğimiz bu bir morse alfabesidir. Bu sesi ancak morse decoder ile kırmamız gerek ve bunun için de en iyi site [Morse Code Adaptive Audio Decoder | Morse Code World](https://morsecode.world/international/decoder/audio-decoder-adaptive.html)

![alt text](Images/image-57.png)

***THM{M_O_R_S_E_Y_E_S}***

**1.2 Sabır acıdır ama meyvesi tatlıdır.** 
[Görev dosyası](Text/text-1.txt)

**ÇÖZÜM**

Görev dosyasını indirelim. 

![alt text](Images/image-58.png)

Bir sürü 1 ve 0 var. Binary decoder ile kıralım.

![alt text](Images/image-59.png)

Çıktı olarak bize farklı bir şifreleme verdi. Şimdi bunu da analiz edip şifreleme algoritmasının ne olduğunu öğrenelim.

![alt text](Images/image-60.png)

Şifreleme algoritmasının brainfuck olduğunu öğrendik şimdi de şifreyi kıralım.

![alt text](Images/image-61.png)

Uzunca sayılar çıktı. Bunların decimal sayı olduğunu görebiliyoruz. Decimal decoder ile şifreyi kıralım. 

![alt text](Images/image-62.png)

Burada yine bir hash çıktı. Hangi algoritmaya ait olduğunu anlayamadığımızdan dolayı ilk önce analiz edelim.

![alt text](Images/image-63.png)

Base58 olduğunu bulduk şimdi şifreyi kırabiliriz.

![alt text](Images/image-64.png)

İndirilebilir bir dosya çıktı. İndirip açalım.

![alt text](Images/image-65.png)

Linke gidelim. Linke girdiğimizde bize QR kod verdi. QR decoder ile kıralım. En iyi QR decoder sitesi: [Barcode Reader. Free Online Web Application (inliteresearch.com)](https://online-barcode-reader.inliteresearch.com/) 

![alt text](Images/image-66.png)

İlk kısımda QR koda uygun olanı seçip 2. kısımda QR kodumuzu seçiyoruz sonra da read kısmı ile QR kodunu okutacağız.

![alt text](Images/image-67.png)

***THM{CONTINUE_THE_FIGHT}***

**1.3 Cevabınızı dört gözle bekliyorum ????** 
[Görev dosyası](Text/text-2.txt)

**ÇÖZÜM**

Görev dosyasını indirelim. Görev dosyasını indirdiğimizde ufak bir yazı çıkıyor. Fakat flaga dair bir şey yok.

![alt text](Images/image-68.png)

Ama dikkat ederseniz boş alanda yukarıdaki görüntü çıkıyor. Demek ki burada bir yazı var fakat biz göremiyoruz. İşte " stegsnow tool" tam da bunun için var. Terminale şunu yazacağız:

*stegsnow -C -p "1234" newdos.txt  (şifre ipucunda verilişti: 1234)*

![alt text](Images/image-69.png)

***THM{Pleased_to_meet_you}***
***

