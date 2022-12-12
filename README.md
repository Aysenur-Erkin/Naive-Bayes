# Naive-Bayes

## Naive Bayes Nedir ve Tarihçesi?
Naive Bayes, 1700' lü yıllarda yaşamış matematikçi Thomas Bayes' in  Bayes teoremine dayanan ve sınıflandırma problemlerinin çözümünde kullandığımız denetimli öğrenme algoritmasıdır.

Naive Bayes sınıflandırmasında sisteme belirli bir oranda öğretilmiş veri sunulur (Örn: 100 adet). Öğretim için sunulan verilerin mutlaka bir sınıfı/kategorisi bulunmalıdır. Öğretilmiş veriler üzerinde yapılan olasılık işlemleri ile, sisteme sunulan yeni test verileri, daha önce elde edilmiş olasılık değerlerine göre işletilir ve verilen test verisinin hangi kategoride olduğu tespit edilmeye çalışılır. Elbette öğretilmiş veri sayısı ne kadar çok ise, test verisinin gerçek kategorisini tespit etmek o kadar kesin olabilmektedir

## Neden Naive Bayes deniyor?
Naive Bayes algoritması, Naive ve Bayes olmak üzere iki kelimeden oluşur ve şu şekilde tanımlanabilir:

Naive: Belirli bir özelliğin oluşumunun diğer özelliklerin ortaya çıkışından bağımsız olduğunu varsaydığı için Naive olarak adlandırılır. Bu nedenle yüksek yanlılığa (bias) sahiptir.

Bayes: Bayes teoremi ilkesine bağlı olduğu için Bayes olarak adlandırılır.

## Bayes Teoremi
<img src="https://github.com/Aysenur-Erkin/Naive-Bayes/blob/main/bayes.jpg" width="auto">

Bayes Teoremi: B koşulu altında A' nın gerçekleşme olasılığını; A' nın gerçekleşme olasılığı, B' nin gerçekleşme olasılığı ve A koşulu altında B' nin gerçekleşme olasılığını kullanarak bulur.

## Naive Bayes Çalışma Mantığı
Algoritmanın çalışma şekli bir eleman için her durumun olasılığını hesaplar ve olasılık değeri en yüksek olana göre sınıflandırır. Az bir eğitim verisiyle çok başarılı işler çıkartabilir. Elbette öğretilmiş veri sayısı ne kadar çok ise, test verisinin gerçek kategorisini tespit etmek o kadar kesin olabilmektedir.

Bir veri setini kullanarak, bir karar vermemiz gerekiyor. Dolayısıyla bu sorunu çözmek için aşağıdaki adımları izlememiz gerekiyor:

-Verilen veri setini frekans tablolarına (sıklık çizelgesi) dönüştürün.



