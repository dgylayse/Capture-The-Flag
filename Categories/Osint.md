
**SORU 1: OSINT KAZA**  *(6. Ege Siber CTF)*

Yakın zamanda bir arkadaşımız sebebi bilinmeyen bir kaza geçirdi ve maalesef ki şu an kısa süreli hafıza kaybı yaşıyor. Kendisi yoğun bakımdan ilk uyandığını andan itibaren arabasını sayıklıyor ve nerede olduğunu merak ediyor. Bizler de böyle bir durumda kendisine yardımcı olmak istiyoruz. Sadece o gün telefonundan yanlışlıkla bir fotoğraf çekilmiş. Anlaşılan bir kafenin oralarda ve bu fotoğrafta arabasının bir kısmı görünmekte. Arabasının şu an nerede olduğunu bulabilir misin?

*Flag Formatı: FlagKaza{‘………’_Caddesi}*

![alt text](https://github.com/dgylayse/Capture-The-Flag/blob/main/Images/image-0.png)

**ÇÖZÜM:**

[TinEye](https://tineye.com/) ile resimi arattım.

![alt text](https://github.com/dgylayse/Capture-The-Flag/blob/main/Images/image-1.png)

Verilen site bağlantısında İzmirde bir yer olduğunu anladım.  

![alt text](https://github.com/dgylayse/Capture-The-Flag/blob/main/Images/image-2.png)

Resimin daha büyük halinde vintage city yazdığı görülüyor.  Vintage city izmir diye arattım.

![alt text](https://github.com/dgylayse/Capture-The-Flag/blob/main/Images/image-3.png)

Facebookta caddenin adını Süvari olduğunu görüyoruz.

![alt text](https://github.com/dgylayse/Capture-The-Flag/blob/main/Images/image-4.png)

***FlagKaza{‘Süvari’_Caddesi}***
***
**SORU 2: Osint Dojo** *(TryHackMe)*

OSINT Dojo kısa süre önce bir siber saldırının kurbanı oldu. Görünüşe göre büyük bir hasar yok ve sistemlerimizden herhangi birinde başka önemli bir uzlaşma göstergesi görünmüyor. Ancak adli analiz sırasında yöneticilerimiz siber suçlular tarafından geride bırakılan bir görüntü buldular. Belki de saldırganların kim olduğunu belirlememizi sağlayabilecek bazı ipuçları içeriyordur?

Saldırgan tarafından bırakılan görüntüyü kopyaladık, tarayıcınızda [buradan](https://raw.githubusercontent.com/OsintDojo/public/3f178408909bc1aae7ea2f51126984a8813b0901/sakurapwnedletter.svg) görüntüleyebilirsiniz.

*Flag Formatı: THM{}*

**2.1 Saldırgan hangi kullanıcı adını kullanıyor?**

**ÇÖZÜM**

Soruda saldırganın bıraktığı resmin kopyası linkte verilmiştir. Linke basalım.

![alt text](https://github.com/dgylayse/Capture-The-Flag/blob/main/Images/image-9.png)

Linke basınca aşağıdaki görüntüden başka bir şey yok. 

![alt text](https://github.com/dgylayse/Capture-The-Flag/blob/main/Images/image-10.png)

Bu tür durumlarda ilk başvurmamız gereken şey sayfanın kaynak kodlarıdır. Faremiz ile sağa tıklayıp inceleye basalım. 

![alt text](https://github.com/dgylayse/Capture-The-Flag/blob/main/Images/image-11.png)

Ve burada saldırganın kullanıcı adını bulmuş bulunmaktayız. 

![alt text](https://github.com/dgylayse/Capture-The-Flag/blob/main/Images/image-12.png)

***THM{SakuraSnowAngelAiko}***

Görünüşe göre saldırganımız operasyonel güvenliklerinde ölümcül bir hata yapmış. Kullanıcı adlarını diğer sosyal medya platformlarında da tekrar kullanmış görünüyorlar. Bu, diğer sosyal medya hesaplarını bularak onlar hakkında ek bilgi toplamamızı çok daha kolay hale getirecektir.

Çoğu dijital platformda bir çeşit kullanıcı adı alanı vardır. Pek çok kişi kullanıcı adlarına bağlanır ve bu nedenle onu bir dizi platformda kullanabilir, bu da kullanıcı adı yeterince benzersiz olduğunda aynı kişiye ait diğer hesapları bulmayı kolaylaştırır. Bu, özellikle iş arama siteleri gibi, kullanıcının tam adı veya konum bilgileri gibi kendisi hakkında gerçek bilgiler verme olasılığının daha yüksek olduğu platformlarda faydalı olabilir.

Saygın bir arama motorunda yapılacak hızlı bir arama, diğer platformlardaki eşleşen kullanıcı adlarını bulmaya yardımcı olabilir ve aynı amaç için var olan çok sayıda özel araç da vardır. Bazen bir platformun yanlış negatifler nedeniyle arama motoru sonuçlarında veya özel kullanıcı adı aramalarında görünmeyeceğini unutmayın. Bazı durumlarda, hesabın var olup olmadığından %100 emin olmak için siteyi kendiniz manuel olarak kontrol etmeniz gerekir. Aşağıdaki soruları yanıtlamak için, saldırgan hakkında ek tanımlayıcı bilgiler toplamak amacıyla OSINT araştırmasını diğer platformlara genişletmek için Görev 2'de bulunan saldırganın kullanıcı adını kullanın. Yanlış pozitiflere karşı dikkatli olun!

**2.2 Saldırgan tarafından kullanılan tam e-posta adresi nedir?**

**ÇÖZÜM**

Bilgilendirme kısmında da bahsettiği gibi bir kullanıcı adı ile birçok bilgiye ulaşabiliriz. Bulduğumuz kullanıcı adı ile googlede aratalım. 

![alt text](https://github.com/dgylayse/Capture-The-Flag/blob/main/Images/image-13.png)

İlk önce bir GitHuba girelim. Sayfayı ilk açtığımda gözüme ilk ilişen PGP Keys oldu. Buna bir bakalım. 

![alt text](https://github.com/dgylayse/Capture-The-Flag/blob/main/Images/image-14.png)

Buradan View code kısmına bakalım. Buradan da publickey denen kısma basalım.  

![alt text](https://github.com/dgylayse/Capture-The-Flag/blob/main/Images/image-15.png)

Burada bize uzunca bir hash verdiğini görüyoruz.

![alt text](https://github.com/dgylayse/Capture-The-Flag/blob/main/Images/image-16.png)

Hashın ilk satırında (----BEGIN PGP PUBLİC KEY BLOCK-----) da  anlaşılacağı üzere bu hash PGP algoritmasınındır. Şimdi bu hashı çözelim bakalım bize ne tür bilgiler verecek. Googleye pgp decoder yazıp ilk siteye girin. Hashın kodunu çözün. 

![alt text](https://github.com/dgylayse/Capture-The-Flag/blob/main/Images/image-17.png)

Ve işte saldırganın mail hesabı:

![alt text](https://github.com/dgylayse/Capture-The-Flag/blob/main/Images/image-18.png)

***THM{SakuraSnowAngel83@protonmail.com}***

**2.3 Saldırganın tam gerçek adı nedir?**

**ÇÖZÜM**

Saldırganın kullanıcı adını tekrar googleden aradığımızda bir linkedin hesabının olduğu anlaşılıyor.

![alt text](https://github.com/dgylayse/Capture-The-Flag/blob/main/Images/image-19.png)

***THM{Aiko Abe}***

Görünüşe göre siber suçlular peşlerinde olduğumuzun farkındalar. Github hesaplarını araştırırken, hesap sahibinin bizi izlerinden uzaklaştırmak için bilgileri düzenlemeye ve silmeye başladığına dair göstergeler gözlemledik. Muhtemelen bu bilgileri soruşturmamıza katkıda bulunacak bazı veriler içerdiği için kaldırıyorlardı. Belki de sağladıkları orijinal bilgileri geri almanın bir yolu vardır?

Bazı platformlarda, sayfa başka bir platformda önbelleğe alınmadığı veya arşivlenmediği sürece düzenlenen veya kaldırılan içerik kurtarılamayabilir. Bununla birlikte, diğer platformlar düzenleme, silme veya ekleme geçmişini görüntülemek için yerleşik işlevselliğe sahip olabilir. Mevcut olduğunda, bu denetim geçmişi müfettişlerin bir zamanlar muhtemelen yanlışlıkla veya dikkatsizlik sonucu eklenen ve daha sonra kullanıcı tarafından kaldırılan bilgileri bulmasına olanak tanır. Bu tür içerikler genellikle bir soruşturma sırasında oldukça değerlidir. Aşağıdaki soruları yanıtlamak için, değiştirilmiş veya kaldırılmış olabilecek ek bilgiler için saldırganın Github hesabına daha derin bir dalış yapmanız gerekecektir. Daha sonra bu bilgileri saldırganın bazı kripto para işlemlerinin izini sürmek için kullanacaksınız.

**2.4 Saldırgan hangi kripto para birimi cüzdanına sahiptir?**

**ÇÖZÜM**

Bize böyle bir bilgi verilmiştir. Bu da oluyor ki saldırgan onu takip ettiğimizin farkında ve bazı yerlerden birtakım bilgileri kaldırmış.  Yukarıdaki bilginin de bahsettiği gibi bazı platformlarda silme düzenleme ekleme geçmişi görüntülenebiliyor. Github da bu platformlardan biridir. 

Tekrardan saldırganın github hesabına girelim. Buradan github deposuna girip detaylıca bir inceleyelim. 

![alt text](https://github.com/dgylayse/Capture-The-Flag/blob/main/Images/image-20.png)

Buradan ETH deposuna girelim. *(ETH, ERC-20 kod sistemi sayesinde birçok kripto para biriminin altyapısını oluşturan merkeziyetsiz ve açık kaynak kodlu bir blok zinciridir.)*

![alt text](https://github.com/dgylayse/Capture-The-Flag/blob/main/Images/image-21.png)

Burada bir script vermiş onu açalım.

![alt text](https://github.com/dgylayse/Capture-The-Flag/blob/main/Images/image-22.png)

Sağ üstte 23.01.2021 yılı için bir geçmiş gösteriyor oraya bakalım.

![alt text](https://github.com/dgylayse/Capture-The-Flag/blob/main/Images/image-23.png)

Üsttekine bakalım. 

![alt text](https://github.com/dgylayse/Capture-The-Flag/blob/main/Images/image-24.png)

Burada kırmızı renkle gösterilen kısım silinmiş alan.  Sarı renk ile vurguladığım kısmı googleden aratalım. 

![alt text](https://github.com/dgylayse/Capture-The-Flag/blob/main/Images/image-25.png)

Arattığımızda hemen ikinci sitede kripto para birimi ismi gözükmektedir.

![alt text](https://github.com/dgylayse/Capture-The-Flag/blob/main/Images/image-27.png)

***THM{Ethereum}***

**2.5 Saldırganın kripto para cüzdan adresi nedir?**

**ÇÖZÜM**

Üstteki resimde kırmızı kısım bu sorunun cevabı. 

***THM{0xa102397dbeeBeFD8cD2F73A89122fCdB53abB6ef}***

**2.6 Saldırgan 23 Ocak 2021 UTC'de hangi madencilik havuzundan ödeme aldı?**

**ÇÖZÜM**

![alt text](https://github.com/dgylayse/Capture-The-Flag/blob/main/Images/image-28.png)

***THM{Ethermine}***

**2.7 Saldırgan kripto para birimi cüzdanını kullanarak başka hangi kripto para birimini değiştirdi?**

**ÇÖZÜM**

Saldırganın kripto para cüzdan adresini googleden arattığımıza ikinci siteyi açalım. Siteyi açtığımızda karşımıza bir arama çubuğu var .

![alt text](https://github.com/dgylayse/Capture-The-Flag/blob/main/Images/image-29.png)

Buraya **“0xa102397dbeeBeFD8cD2F73A89122fCdB53abB6ef"** yapıştıralım. Karşımıza çıkan sayfada işaretlediğim kısıma basalım. 

![alt text](https://github.com/dgylayse/Capture-The-Flag/blob/main/Images/image-30.png)

Sayfa bize hesap hareketlerini gösteriyor. Biraz sayfayı inceleyelim. İncelediğimizde burada faklı bir kripto para birimini görmekteyiz. 

![alt text](https://github.com/dgylayse/Capture-The-Flag/blob/main/Images/image-31.png)

***THM{Tether}***

Tam da düşündüğümüz gibi, siber suçlular saldırılarından sonra onlar hakkında bilgi topladığımızın tamamen farkındadır. Hatta Twitter'da OSINT Dojo'ya mesaj atacak ve çabalarımız için bizimle alay edecek kadar yüzsüzdüler. Kullandıkları Twitter hesabı daha önce takip ettiğimizden farklı bir kullanıcı adı kullanıyor gibi görünüyor, belki de bir sonraki adımda nereye gideceklerine dair bir fikir edinmek için bulabileceğimiz bazı ek bilgiler vardır?

Saldırgan tarafından bize gönderilen mesajın ekran görüntüsünü aldık, tarayıcınızda [buradan](https://raw.githubusercontent.com/OsintDojo/public/main/taunt.png) görüntüleyebilirsiniz.

Birçok kullanıcı kullanıcı adını farklı platformlarda paylaşsa da, kullanıcıların soruşturma, trolleme veya kişisel ve kamusal yaşamlarını ayırmanın bir yolu olarak tamamen ayrı tuttukları alternatif hesaplara sahip olmaları nadir değildir. Bu alternatif hesaplar, diğer hesaplarında görülmeyen bilgiler içerebilir ve ayrıca iyice araştırılmalıdır. Aşağıdaki soruları yanıtlamak için, saldırgan tarafından Twitter'daki OSINT Dojo'ya gönderilen mesajın ekran görüntüsünü görüntülemeniz ve saldırganın Twitter hesabında ek bilgi bulmak için kullanmanız gerekecektir. Daha sonra, ek bilgileri keşfetmek için Twitter hesabından Dark Web'e ve diğer platformlara giden yolları takip etmeniz gerekecektir.

**2.8 Saldırganın şu anki Twitter tanıtıcısı nedir?**

**ÇÖZÜM**

Saldırgan tarafından bize gönderilen mesaja bakalım. 

![alt text](https://github.com/dgylayse/Capture-The-Flag/blob/main/Images/image-32.png)

Saldırganın mesajı: "Ne yaptığını görmediğimi sanma! Beni yakalamayacaksın BTW. Ben zaten gidiyorum . Evine dön, baaaayyyyy! " 

![alt text](https://github.com/dgylayse/Capture-The-Flag/blob/main/Images/image-33.png)

Resimdeki kullanıcı adını twitterda aratalım.  Karşımıza böyle bir tweet çıkıyor. Tweeti atan kullanıcının sayfasına gidelim. 

![alt text](Images/image-34.png)

Ve karşımızda  şuanki Twitter tanıtıcısı :

![alt text](https://github.com/dgylayse/Capture-The-Flag/blob/main/Images/image-35.png)

***THM{SakuraLoverAiko}***

**2.9 Saldırganın WiFi SSID'lerini ve şifrelerini kaydettiği konumun URL'si nedir?**

**ÇÖZÜM**

Saldırganın tweetlerini incelediğimizde şöyle bir tweet karşımıza çıkıyor:

![alt text](https://github.com/dgylayse/Capture-The-Flag/blob/main/Images/image-36.png)

Tweet : **"Artık yeni telefonlar aldığımda Ap’lerimi unutmak yok!”*  Saldırgan bu tweetin altına bir tweet daha atmış. Ve burada DEEP PASTE büyük yazmış.

![alt text](https://github.com/dgylayse/Capture-The-Flag/blob/main/Images/image-37.png)

Bu da demek oluyor ki deep webden DeepPaste sitesine gidip tweette verilen hashı orada aratmak. 

![alt text](https://github.com/dgylayse/Capture-The-Flag/blob/main/Images/image-38.png)

Ben bayağı duckduckgo üzerinden bu siteyi aradım bulamadım. Zaten ipucunda deep webe girmek istemeyenler için link vermiş. Biz oradan yararlanalım. 

![alt text](https://github.com/dgylayse/Capture-The-Flag/blob/main/Images/image-39.png)

Verilen linke girelim. 

![alt text](https://github.com/dgylayse/Capture-The-Flag/blob/main/Images/image-40.png)

Soru bizden url istiyor.  Üstteki arama çubuğunun yanındaki kutuya da hashı yazacağız ve işteee cevap. 

***THM{http://depasteon6cqgrykzrgya52xglohg5ovyuyhte3ll7hzix7h5ldfqsyd.onion/show.php?md5=0a5c6e136a98a60b8a21643ce8c15a74}***

**2.10 Saldırganın Ev Wifi'si için BSSID nedir?**

**ÇÖZÜM**

Bu soruyu çözmek için wigle.net sitesinden yararlanacağız. Ve aynı zamanda bu soruyu çözebilmeniz için  hesap açmanız gerek. 

![alt text](https://github.com/dgylayse/Capture-The-Flag/blob/main/Images/image-41.png)

Görselde işaretlediğim yere girelim. SSID / Network Name (exact match) yazan kutucuğa “DK1F-G” yazalım.

![alt text](https://github.com/dgylayse/Capture-The-Flag/blob/main/Images/image-42.png)

Ve işte cevap. 

![alt text](https://github.com/dgylayse/Capture-The-Flag/blob/main/Images/image-43.png)

***THM{84:af:ec:34:fc:f8}***

Tweet'lerine bakılırsa, siber suçlumuz gerçekten de iddia ettiği gibi evine dönüyor. Twitter hesaplarında, eve dönüş rotalarını bir araya getirmemizi sağlayacak çok sayıda fotoğraf var gibi görünüyor. Geride bıraktıkları ekmek kırıntılarının izini takip edersek, hareketlerini bir konumdan diğerine ve son varış noktalarına kadar izleyebiliriz. Son duraklarını tespit ettiğimizde, bulgularımızı hangi kolluk kuvvetlerine iletmemiz gerektiğini belirleyebiliriz.

OSINT'te, çoğu zaman net ve kesin bir cevaba işaret eden "dumanı tüten bir silah" yoktur. Bunun yerine, bir OSINT analisti, neyin olası, olası olmayan veya mümkün olduğuna dair bir sonuca varmak için birden fazla istihbarat parçasını sentezlemeyi öğrenmelidir. Bir analist, mevcut tüm verilerden yararlanarak daha bilinçli kararlar verebilir ve hatta belki de veri boşluklarının boyutunu en aza indirebilir. Aşağıdaki soruları yanıtlamak için saldırganın Twitter hesabından toplanan bilgilerin yanı sıra soruşturmanın önceki bölümlerinden elde edilen bilgileri kullanarak saldırganın ev dediği yere kadar izini sürün.

**2.11 Saldırganın uçuşa binmeden önce fotoğraf paylaştığı konuma en yakın havaalanı hangisidir?**

**ÇÖZÜM**

Saldırganın tweetlerinden birinde uçağa binmeden önce paylaştığı fotoğraf var. 

![alt text](https://github.com/dgylayse/Capture-The-Flag/blob/main/Images/image-44.png)

Tweette Bethesda’da olduğunu söylüyor. Hemen googleden “Bethesda airport” diye aratalım.

![alt text](https://github.com/dgylayse/Capture-The-Flag/blob/main/Images/image-45.png)

***THM{DCA}***

**2.12 Saldırganın son yatışı hangi havaalanındaydı?**

**ÇÖZÜM**

Saldırganın tweetlerinden birinde bir otel var. 

![alt text](https://github.com/dgylayse/Capture-The-Flag/blob/main/Images/image-46.png)

Otelin üzerinde yazan yazıyı hemen googlede aratalım.  

![alt text](https://github.com/dgylayse/Capture-The-Flag/blob/main/Images/image-47.png)

Burada Haneda bilgisine ulaşıyoruz. 

***THM{HND}***

**2.13 Saldırganın son uçuşunda olduğu gibi paylaştığı haritada hangi göl görülebilir?**

**ÇÖZÜM**

Tweetindeki haritadan yararlanacağız. 

![alt text](https://github.com/dgylayse/Capture-The-Flag/blob/main/Images/image-48.png)

Bu görseli web'de arayalım. 

![alt text](https://github.com/dgylayse/Capture-The-Flag/blob/main/Images/image-49.png)

Karşımıza böyle bir sayfa gelecek. 

![alt text](https://github.com/dgylayse/Capture-The-Flag/blob/main/Images/image-50.png)

Buradan haritalara girelim. Haritalar kısmında katmanlar kısmından uydu görünüm yapalım çünkü sorudaki görsel de uydu görünümdedir bulmamız daha kolaylaşır. 

![alt text](https://github.com/dgylayse/Capture-The-Flag/blob/main/Images/image-51.png)

Biraz inceleyerek görselde verilen kısmı bulabiliriz.  

![alt text](https://github.com/dgylayse/Capture-The-Flag/blob/main/Images/image-52.png)

***THM{Lake Inawashiro}***

**2.14  Saldırgan muhtemelen hangi şehri "ev" olarak görüyor?**

**ÇÖZÜM**

Tekrar wigle.net sitesine gidelim.  

![alt text](https://github.com/dgylayse/Capture-The-Flag/blob/main/Images/image-53.png)

Sonra :

![alt text](https://github.com/dgylayse/Capture-The-Flag/blob/main/Images/image-54.png)

Önceki görevde bulduğumuz BSSID buraya yazalım. 

![alt text](https://github.com/dgylayse/Capture-The-Flag/blob/main/Images/image-55.png)

Veee sorumuzun cevabı burada.

![alt text](https://github.com/dgylayse/Capture-The-Flag/blob/main/Images/image-56.png)

***THM{Hirosaki}***
***
