# Bulanık Mantık Kullanarak Borsa Tahmini

Kodlar Python3 ile Jupyter Notebook üzerinde yazılmıştır. Farklı formattaki veri setlerini kullanmak için kodda gerekli değişiklikleri yapmanız gerekir. Amaç son kullanıcıya karşılık bir ürün oluşturmak olmadığından bulanık mantığın uygulanması haricindeki kısımlar arkaplana atılmıştır.

Bulanık mantık kullanarak borsa tahmini yapmak için daha önce yapılmış çalışmaların ilgimi çekmesi üzerine ben de bununla ilgili bir çalışma yapmak istedim. Yapılan çalışmalara göre sonuçlar çeşitlilik göstermekte. Bazı hisselerde %300'e kadar kazanç sağlanmakta iken bazı hisselerde -%70'e kadar kaybettirmekte. Ve bu sonuçlar 3 sene için geçerli. Borsa ile uğraşan kişiler genelde uzun vadeleri sevmeyen kişilerdir ve dalgalı piyasaları severler. Ben de  bunu hem uzun hem de kısa vadede deneyerek gözlemlemeye çalıştım.

**Kullanılan Yöntemler**
Çalışmada bulanık girişler olarak Üssel Hareketli Ortalama, RSI, Bollinger Bantları ve kendi yazmış olduğum basit bir destek indikatörü kullandım.

Üyelik fonksiyonları oluşturma kısmında ise her piyasanın standard sapmasından, hisse senedi fiyatından ve fiyatların daha çok son günlerdeki değerlerinin daha etkili olduğunu göz önünde bulundurarak dinamik bir şekilde oluşturulmasını sağladım. Kuvvetli Al, Al, Bekle, Sat, Kuvvetli Sat olmak üzere beş üyelik fonksiyonu kullandım. Üyelik fonksiyonları yarım üçgen ve üçgenlerden oluşmakta. Yamuk üyelik fonksiyonunu da denedim ama üçgen daha etkili sonuç verdi.

Çıkış üyelik fonksiyonları gene yarım üçgen ve üçgenlerden oluşan Kuvvetli Al, Al, Bekle, Sat, Kuvvetli Sat şeklinde beş sonuç üretmekte.

Bulanık sonuç çıkarmada product ve gerektirme yöntemlerini kullandım

Durulaştırmada ise maksimum yöntemini kullandım

**Zorluklar**
* Piyasalar ani siyasi ve ekonomik olaylardan çok hızlı etkilenirken bunu makine ortamında modellemek veya tahmin etmek çok zor

* Hem indikatörler her zaman doğru sonuç üretmezler, yani kendi hataları söz konusudur. Birden fazla indikatör kullanıldığı için buların hataları bir indikatörün doğru veya yanlış aldıkları kararlar diğer indikatörlerden kuvvetli bir şekilde desteklene veya reddedilebilir

* Blanık Mantık bulanık girişler ister ama indikatörler genelde klasik kümelerle sonuç döndürür. Bundan dolayı indikatör sonuçlarının bulanıklaştırılması lazım ve bu aşamada benim oluşturduğum bulanıklaştırma modellerinin bir hatası söz konusu ve bu hatanın hesaplanacağı bir referans bulunmamakta.

* Üyelik fonksiyonunun doğru şekilde belirlenme zorluğu.

* Kuralların doğru belirlenme zorluğu


**Sonuç**

Sonuç olarak yapılan testlerde maksimum kayıp -%20, maksimum kazanç ise %220' lere kadar çıkabilmekte. Elde edilen bu sonuçlar farklı vadelerde test edilmiştir. Kısa vadelerde genelde kazanç gözlemlenememiştir.
Piyasalar genelde fiyatlar yükseliş eğilminde olduğundan 3 sene gibi uzun vadelerde kar zaten %200 veya daha yükseklere çıka bilmekte.

Dolayısı ile iyi sonuçlar elde edebilmek için yukarıda bahsedilen zorlukların doğru bir şekilde modelleme ve hatta gerekirse uzman kişilerden danışmanlık alınması gerekir.
