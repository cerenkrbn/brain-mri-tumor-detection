 Brain MRI Tümör Tespiti Projesi

 Proje Hakkında
Bu proje, Kaggle’daki [Brain MRI Images for Brain Tumor Detection](https://www.kaggle.com/datasets/navoneel/brain-mri-images-for-brain-tumor-detection) veri setini kullanarak **beyin MRI görüntülerinden tümör var/yok sınıflandırması** yapmayı amaçlamaktadır.  
Derin öğrenme tabanlı **Convolutional Neural Network (CNN)** modeli ile küçük bir veri setinde erken teşhis için umut vadeden sonuçlar elde edilmiştir.

---

 Veri Seti
- Kaynak: Kaggle  
- Sınıflar:  
  - Yes → Beyin tümörü var  
  - No → Beyin tümörü yok  
- Toplam Görüntü Sayısı: ~250  
- Bölünme Oranı: %70 Eğitim | %15 Doğrulama | %15 Test  

---

 Kullanılan Yöntemler
- Ön İşleme :
  - Görselleri grayscale formatına çevirme  
  - 224×224 boyutuna yeniden ölçekleme  
  - Normalizasyon (0–1 arası değerler)  
- Veri Artırma (Data Augmentation):  
  - Yatay çevirme, küçük açılarla döndürme, zoom uygulamaları  
- Model Mimarisi (CNN):  
  - Conv2D + ReLU + MaxPooling katmanları  
  - Dropout (overfitting’i engellemek için)  
  - Dense (sigmoid aktivasyon) ile binary sınıflandırma  
- Callback’ler:  
  - EarlyStopping  
  - ReduceLROnPlateau  
  - ModelCheckpoint  

---

 Sonuçlar:
- Test Accuracy (Doğruluk): ~%60  
- Test AUC: ~0.77  
- Model, küçük veri setine rağmen anlamlı bir ayırma gücü göstermiştir.  

### Şekil 1. Eğitim ve Doğrulama Doğruluk Eğrileri
![Accuracy Curve](assets/accuracy_curve.png)

---

Karşılaşılan Zorluklar:
- Küçük ve dengesiz veri seti nedeniyle genelleme sınırlı kaldı  
- Her çalıştırmada farklı train/validation split → accuracy dalgalanmaları  
- GPU uyarıları (küçük batch ile optimize edildi)  

---

 Gelecek Çalışmalar:
- Daha güçlü **transfer learning** modelleri (MobileNetV2, ResNet50, VGG16) ile performans artırma  
- Data augmentation çeşitlerini genişletme  
- **Grad-CAM** gibi tekniklerle modelin karar verdiği bölgeleri görselleştirme  
- Basit bir **web uygulaması (Streamlit/Flask)** üzerinden kullanıcı dostu arayüzle çalıştırma  

---

 Faydalı Linkler:
- 📘 [Kaggle Notebook](https://www.kaggle.com/code/cerenkurban/ceren-kurban)  
- 📊 [Dataset](https://www.kaggle.com/datasets/navoneel/brain-mri-images-for-brain-tumor-detection)

---

  Katkıda Bulunan:
Bu proje, yapay zeka ve veri bilimi alanındaki ilgim doğrultusunda geliştirilmiştir.  
Amacım, küçük bir tıbbi görüntü veri seti üzerinde derin öğrenme yöntemlerini deneyimlemek, modelleme sürecini öğrenmek ve Kaggle–GitHub iş akışıyla projeyi uçtan uca yönetmektir.


---

 📜 Lisans
MIT License

