**SORU 1: Stego / Neredeyim ?**  *(6. Ege Siber CTF)*

Benim nerede olduğumu bulabilecek misin?

*Flag Formatı: EGESIBER{}*

![alt text](Images/image-8.png)

**ÇÖZÜM:**

Sorunun vermiş olduğu görseli indirdim. [AperiSolve](https://www.aperisolve.com/) aracı ile inceledim.

![alt text](Images/image-5.png)

Exiftool kısmından GPS bilgisi olduğunu gördüm ve [bu siteden](https://www.latlong.net/degrees-minutes-seconds-to-decimal-degrees) bunu konum olarak dönüştürdüm:

![alt text](Images/image-6.png)

Bulduğumuz (36° 31' 50.4100'' N 29° 7' 37.9200'' E)  konumunu googleda aratıyorum ve google karşıma konumu getiriyor ve böylece flagin "Kidrak koyu" olduğunu anlıyoruz:

![alt text](Images/image-7.png)

***EGESIBER{Kıdrak Koyu}***
***