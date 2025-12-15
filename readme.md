# Genetik Algoritma ile Öğrenci Etüt Programı Optimizasyonu

Bu proje, **"Öğrenci Etüt Programı Planlaması" (Senaryo 9)** kapsamında, bir öğrencinin Matematik ve Fen derslerine ayıracağı çalışma sürelerini optimize ederek sınav başarısını maksimize etmeyi amaçlayan bir **Genetik Algoritma (GA)** uygulamasıdır.

## Proje Özeti

Proje, klasik bir **kısıtlı optimizasyon** problemini çözer. Algoritma, öğrencinin çalışma saatlerini belirli kurallar (kısıtlar) çerçevesinde ayarlayarak en yüksek başarı puanını hedefler.

Kısıt ihlalleri (örneğin toplam sürenin aşılması), **Ceza Fonksiyonu (Penalty Function)** yöntemiyle skordan düşülerek yönetilir.

## Matematiksel Model

Problemin matematiksel formülasyonu şöyledir:

### 1. Amaç Fonksiyonu (Maximize)
Başarı skorunu maksimize eden formül:

$$f(x_1, x_2) = 4x_1 + 5x_2 - 0.5x_1^2 - 0.2x_2^2$$

Burada:
* **$x_1$**: Matematik çalışma saati ($0 \le x_1 \le 10$).
* **$x_2$**: Fen çalışma saati ($0 \le x_2 \le 10$).

### 2. Kısıtlar (Constraints)
Çözümün geçerli sayılması için gereken koşullar:
1.  **Toplam Süre Kısıtı:** $x_1 + x_2 \le 12$
2.  **Minimum Fen Süresi:** $x_2 \ge 2$

## Algoritma Konfigürasyonu

Kod içerisinde kullanılan Genetik Algoritma parametreleri şunlardır:

| Parametre | Değer | Açıklama |
| :--- | :--- | :--- |
| **Popülasyon Büyüklüğü** | 50 | Her nesildeki çözüm adayı sayısı. |
| **İterasyon Sayısı** | 100 | Algoritmanın kaç nesil boyunca evrileceği. |
| **Seçim Yöntemi** | Turnuva | Rastgele seçilen 3 adaydan en iyisi ebeveyn olur. |
| **Çaprazlama** | Tek Noktalı | %80 ihtimalle gen takası yapılır. |
| **Mutasyon Şansı** | 0.15 | Genlerin rastgele değişime uğrama olasılığı. |
| **Elitizm** | Var | Her neslin en iyi bireyi doğrudan bir sonrakine aktarılır. |

## Kurulum ve Çalıştırma

### 1. Gerekli Kütüphaneler
Projenin çalışması için `numpy` ve `matplotlib` kütüphaneleri gereklidir:
```bash
pip install numpy matplotlib

2. Kodun Çalıştırılması
yapay_zeka_ilk_ödev.ipynb dosyasını Jupyter Notebook veya Google Colab üzerinde çalıştırabilirsiniz.

Çıktılar
Kod çalıştırıldığında optimizasyon sonucunu gösteren metinler ve performans grafiği üretilir:

Metin Sonuçları:

Önerilen Matematik ve Fen çalışma süreleri.

Toplam çalışma süresi.

Elde edilen maksimum başarı skoru.

Kısıtların (Süre ve Min. Fen) sağlanıp sağlanmadığının kontrolü.

Grafiksel Analiz (Fitness Evrimi):

Algoritmanın nesiller boyunca "En İyi Skoru" nasıl geliştirdiğini gösteren zaman serisi grafiği. Bu grafik, algoritmanın öğrenme ve yakınsama başarısını görselleştirir.

Dosya Yapısı
yapay_zeka_ilk_ödev.ipynb: Python kaynak kodları (Jupyter Notebook).
