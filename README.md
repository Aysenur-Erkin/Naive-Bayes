# Naive-Bayes

## Naive Bayes Nedir ve Tarihçesi?
Naive Bayes, 1700' lü yıllarda yaşamış matematikçi Thomas Bayes' in  Bayes teoremine dayanan ve sınıflandırma problemlerinin çözümünde kullandığımız denetimli öğrenme algoritmasıdır.

Naive Bayes sınıflandırmasında sisteme belirli bir oranda öğretilmiş veri sunulur (Örn: 100 adet). Öğretim için sunulan verilerin mutlaka bir sınıfı/kategorisi bulunmalıdır. Öğretilmiş veriler üzerinde yapılan olasılık işlemleri ile, sisteme sunulan yeni test verileri, daha önce elde edilmiş olasılık değerlerine göre işletilir ve verilen test verisinin hangi kategoride olduğu tespit edilmeye çalışılır. Elbette öğretilmiş veri sayısı ne kadar çok ise, test verisinin gerçek kategorisini tespit etmek o kadar kesin olabilmektedir

## Neden Naive Bayes deniyor?
Naive Bayes algoritması, Naive ve Bayes olmak üzere iki kelimeden oluşur ve şu şekilde tanımlanabilir:

**Naive:** Belirli bir özelliğin oluşumunun diğer özelliklerin ortaya çıkışından bağımsız olduğunu varsaydığı için Naive olarak adlandırılır. Bu nedenle yüksek yanlılığa (bias) sahiptir.

**Bayes:** Bayes teoremi ilkesine bağlı olduğu için Bayes olarak adlandırılır.

## Bayes Teoremi
<img src="https://github.com/Aysenur-Erkin/Naive-Bayes/blob/main/Images/bayes.jpg" width="auto">

**Bayes Teoremi:** Bayes teoremi, olasılık kuramı içinde incelenen önemli bir konudur. Bu teorem bir rassal değişken için olasılık dağılımı içinde koşullu olasılıklar ile marjinal olasılıklar arasındaki ilişkiyi gösterir. Bu şekli ile Bayes teoremi kabul edilir bir ilişkiyi açıklar. Olasılık teorisi içinde incelenen bir olay olarak B olayına koşullu bir A olayı (yani B olayının bilindiği halde A olayı) için olasılık değeri, A olayına koşullu olarak B olayı (yani A olayı bilindiği haldeki B olayı) için olasılık değerinden farklıdır. Ancak bu iki birbirine ters koşulluluk arasında çok belirli bir ilişki vardır ve bu ilişkiye Bayes Teoremi denilmektedir. B koşulu altında A' nın gerçekleşme olasılığını; A' nın gerçekleşme olasılığı, B' nin gerçekleşme olasılığı ve A koşulu altında B' nin gerçekleşme olasılığını kullanarak bulur.

P(A|B): B olayı bilindiğinde A olayının gerçekleşme olasılığı

P(B|A): A olayı bilindiğinde B olayının gerçekleşme olasılığı

P(A): A olayının gerçekleşme olasılığı

P(B): B olayının gerçekleşme olasılığı

## Naive Bayes Çalışma Mantığı
Algoritmanın çalışma şekli bir eleman için her durumun olasılığını hesaplar ve olasılık değeri en yüksek olana göre sınıflandırır. Az bir eğitim verisiyle çok başarılı işler çıkartabilir. Elbette öğretilmiş veri sayısı ne kadar çok ise, test verisinin gerçek kategorisini tespit etmek o kadar kesin olabilmektedir.

Bir veri setini kullanarak, bir karar vermemiz gerekiyor. Dolayısıyla bu sorunu çözmek için aşağıdaki adımları izlememiz gerekiyor:
- Verilen veri setini frekans tablolarına (sıklık çizelgesi) dönüştürün.
- Verilen özelliklerin olasılıklarını bularak olabilirlik tablosu (likelihood table) oluşturun.
- Son olarak, sonsal olasılığı (posterior probability) hesaplamak için Bayes teoremini kullanın.

## Naive Bayes Örnek
Sorun: Hava güneşliyse oyuncu oynamalı mı oynamamalı mı?

Çözüm: Bunu çözmek için öncelikle aşağıdaki veri setini göz önünde bulundurmamız lazım.

<img src="https://github.com/Aysenur-Erkin/Naive-Bayes/blob/main/Images/1.png" width="750" heigth="750">

**Hava Koşulları İçin Frekans Tablosu:**

<img src="https://github.com/Aysenur-Erkin/Naive-Bayes/blob/main/Images/2.png" width="750" heigth="750">

**Likelihood Tablosu:**

<img src="https://github.com/Aysenur-Erkin/Naive-Bayes/blob/main/Images/3.png" width="750" heigth="750">

**Bayes Teoremini Uygularsak:**

P(Yes|Sunny)= P(Sunny|Yes)*P(Yes)/P(Sunny)

P(Sunny|Yes)= 3/10= 0.3

P(Sunny)= 0.35

P(Yes)=0.71

P(Yes|Sunny) = 0.3*0.71/0.35= 0.60

P(No|Sunny)= P(Sunny|No)*P(No)/P(Sunny)

P(Sunny|No)= 2/4=0.5

P(No)= 0.29

P(Sunny)= 0.35

P(No|Sunny)= 0.5*0.29/0.35 = 0.41

P(Yes|Sunny)>P(No|Sunny)

**Dolayısıyla, Güneşli bir günde, Oyuncu oyunu oynayabilir.**

## Zero-Frequency Problemi
**Test kümesindeki bir değerin eğitim kümesinde gözlemlenemeyen bir değeri varsa olasılık değeri olarak 0 verir yani tahmin yapamaz. Bu durum genellikle Zero Frequency (Sıfır Frekans) adıyla bilinir. Bu durumu çözmek için düzeltme teknikleri kullanılabilir. Bunun için en basit yöntem tüm verilere minimum değer ekleyerek (genellikle 1) bu olasılık ortadan kaldırılabilir. Bu duruma Laplace kullanılarak tahminleme de denmektedir.**

## Naive Bayes Sınıflandırıcısının Avantajları:
- Naive Bayes, bir veri kümesi sınıfını tahmin etmek için hızlı ve kolay makine öğrenimi algoritmalarından biridir.
- Diğer Algoritmalara kıyasla çok sınıflı tahminlerde iyi performans gösterir.
- Az veriyle iyi işler başarabilir.
- Sürekli ve kesikli veriler ile kullanılabilir.
- Yüksek boyutlu verilerde iyi çalışabilir.
- Metin sınıflandırma problemlerinde (text classification problems) en popüler seçimdir.

## Naive Bayes Sınıflandırıcısının Dezavantajları:
- Naive Bayes, tüm özelliklerin bağımsız veya ilgisiz olduğunu varsayar, bu nedenle özellikler arasındaki ilişkiyi öğrenemez.
- Kategorik değişkenin test veri setinde, eğitim veri setinde gözlenmeyen bir kategorisi varsa, model 0 (sıfır) olasılık atayacak ve tahmin yapamayacaktır. Bu genellikle "sıfır olasılık sorunu" olarak bilinir.

## Naive Bayes Kullanım Alanları:
- Naive Bayes hızlı bir algoritma olduğu için gerçek zamanlı tahminler yapmak için kullanılabilir.
- Kredi puanlaması için kullanılır.
- Spam filtreleme ve duygu analizi gibi metin sınıflandırmasında kullanılır.
- Tıbbi veri sınıflandırmasında kullanılır.

## Naive Bayes Modeli Türleri:
- **Multinomial Naive Bayes:** Bu daha çok belge sınıflandırma problemi için kullanılır, yani bir belgenin spor, politika, teknoloji vb. kategorisine ait olup olmadığı. Sınıflandırıcı tarafından kullanılan özellikler/tahmin ediciler, belgede bulunan kelimelerin sıklığıdır.
- **Bernoulli Naive Bayes:** Bu, çok terimli naive bayes'e benzer, ancak öngörücüler boolean değişkenlerdir. Sınıf değişkenini tahmin etmek için kullandığımız parametreler sadece evet veya hayır değerlerini alır, örneğin bir kelimenin metinde geçip geçmediği.
- **Gauss Naive Bayes:** Bu algoritmada sürekli veri ele alınır. Her sınıfla ilişkili sürekli özellikler normal (veya Gaussian) dağılıma göre dağıtılır. Bu yöntem kullanılarak eğitim verisinden her sınıf için ortalama (mean) ve standart sapma (standard deviation) değerleri tahmin edilir. Bu sayede dağılım özetlenir.

## Kaynakça
https://towardsdatascience.com/5-minute-machine-learning-naive-bayes-f48472670fdd

https://www.javatpoint.com/machine-learning-naive-bayes-classifier

