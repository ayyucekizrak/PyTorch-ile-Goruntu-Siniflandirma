# :fire: PyTorch ile Görüntü Sınıflandırma 

Bir süredir PyTorch üzerinden pratikler yapmaya çalışıyorum. Caffe ile başlayan yolculuğum, TensorFlow ve Keras ile güzel devam etti ama neden PyTorch'un da nimetlerini öğrenmeyeyim ki diye düşünüyorum. :sunglasses: Geçtiğimiz hafta içinde [People In Data](https://www.facebook.com/peopleindata/) ve [Facebook DevC Stockholm](https://www.facebook.com/groups/devCstockholm/) ortaklığıyla düzenlenen etkinlikte **Udacity AI** mentorlerinden _Pranjal_ ile tanışmış oldum ve harika bir webinar gerçekleştirdi. Tabi hem Pytorch'a ısınmam için hem de bu sırada meraklılarına faydalı olması adına bu notebook'u hazırlamaya karar verdim. Destek veren [Pranjal](https://www.linkedin.com/in/pranjall/?originalSubdomain=in)'a ve bu etkinlik hakkında beni haberdar ettiği için [Zümrüt](https://www.linkedin.com/in/zumrut-muftuoglu-98704537/)e teşekkürler.

Bu Colab Notebookda, Evrişimli Sinir Ağları temellerini kullanarak basit bir görüntü sınıflandırma çalışması uygularken [PyTorch Ekosistemindeki](https://pytorch.org/ecosystem/ "Click to visit the PyTorch Ecosystem homepage") yeniliklerden de faydalanacağız.

### Başlayalım!!! 
<img align="left" src="https://media.giphy.com/media/oio1NtBHjowYE/giphy.gif" width=40% />

📌[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/ayyucekizrak/PyTorch-ile-Goruntu-Siniflandirma/blob/master/PyTorch_ile_G%C3%B6r%C3%BCnt%C3%BC_S%C4%B1n%C4%B1fland%C4%B1rma.ipynb) **Google Colab Not Defterinde Aç**

📌[![Open In Jupyter](https://github.com/jupyter/notebook/blob/master/docs/resources/icon_32x32.svg)](https://nbviewer.jupyter.org/github/ayyucekizrak/PyTorch-ile-Goruntu-Siniflandirma/blob/master/PyTorch_ile_G%C3%B6r%C3%BCnt%C3%BC_S%C4%B1n%C4%B1fland%C4%B1rma.ipynb) **Jupyter Not Defterinde Aç** 


<br/>**İçerik:**
<br/>**1. Colab Üzerinde Veri Setini Veri Setlerini Kullanma**
<br/>**2. Eğitim, Doğrulama/Geçerleme ve Test Kümelerinin Oluşturulması**
<br/>**3. Dataloaderların Hazırlanması**
<br/>**4. PyTorch Kullanarak CNN Modeli Oluşturma**
   <br/>_4.1.1. Evrişimli Sinir Ağı (CNN) Mimarisi
   <br/>4.1.2 Temel bir CNN Katmanı
   <br/>4.1.3 Adım kaydırma (Stride)
   <br/>4.1.4 Piksel Ekleme (Padding)
   <br/>4.1.5 Maksimum Ortaklama (Max-Pooling)
   <br/>4.1.6 Aktivasyon Fonksiyonu: ReLU (Rectified Linear Units)
   <br/>4.1.7 Tam Bağlantılı, Lineer Bağlantılı Katmanlar (Fully Connected or Linear Layers)
   <br/>4.2.1 PyTorch (Gelelim Sadede)
   <br/>4.2.2 Hesaplamalı Grafikleri (Computational Graph) Anlama
   <br/>4.2.3 Tensörler
   <br/>4.2.4 Autograd Modülü
   <br/>4.2.5 nn.Module
   <br/>4.2.6 Optim Paketi
   <br/>4.3 Modelimizi tanımlama zamanı!_
<br/>**5. 2020'de bir PyTorch Modeli Eğitelim** 
<br/>**6. Aşırı Uydurma/Öğrenme (Ezberleme) ya da Overfitting naıl birşeydir anlayalım**   
**7. Daha İyi Bir Eğitim Döngüsü**
<br/>**8. Daha Alımlı Bir Eğitim Döngüsü**
<br/>**9. SONUÇ**
<br/>**10. Teşekkürler**

---

_Gently Thanks to [Pranjal](https://www.linkedin.com/in/pranjall/?originalSubdomain=in) for awesome webinar and thanks to [Zümrüt](https://www.linkedin.com/in/zumrut-muftuoglu-98704537/) for invited me to the webinar_ 
<br/>Not:
https://github.com/pranjalchaubey/Deep-Learning-Notes
