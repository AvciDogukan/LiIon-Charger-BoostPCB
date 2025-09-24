# 🔋 Li-Ion Pil Şarj ve 5V Boost Dönüştürücü PCB

## 📌 Proje Özeti
Bu proje, **USB üzerinden Li-Ion pil şarjı** ve aynı anda **5V çıkış sağlayan** kompakt bir PCB tasarımıdır.  
- **TP4056** entegresi ile güvenli pil şarjı yapılır.  
- **TPS61040** boost konvertör sayesinde pil voltajı (3.0–4.2V) sabit 5V’a yükseltilir.  
- Çıkış **USB-A portu** üzerinden alınır.  
- LED indikatörler şarj/dolu durumunu gösterir.  

---

## 📐 Devre Şeması
![Schematic](images/schematic.png)

---

## 🖼️ PCB Görünümü
![PCB Layout](images/pcb.png)

## 🖼️ 3D View Görünümü
![PCB Layout](images/3Dview.png)

## 🖼️ 2D View Görünümü
![PCB Layout](images/2Dview.png)
---

## 🔧 Teknik Özellikler
- **Giriş**: 5V (USB Micro-B)  
- **Pil**: Tek hücre Li-Ion (3.7V nominal, 4.2V tam dolu)  
- **Şarj Akımı**: TP4056 üzerinden programlanabilir (Rprog ile ayarlanır)  
- **Boost Konvertör**: TPS61040 (sabit 5V çıkış)  
- **Koruma**: Zener diyot + Schottky diyot  
- **LED Durumları**:  
  - 🔴 Kırmızı → Şarj oluyor  
  - 🟢 Yeşil → Şarj tamamlandı  

---

## 📦 Malzeme Listesi (BOM)
- U3 → TP4056 Li-Ion Charger IC  
- U2 → TPS61040 Boost Converter  
- D1 → Schottky Diyot (MBR0530)  
- ZD1 → 5.1V Zener Diyot  
- L1 → 100µH Endüktör  
- Rprog (R1) → Şarj akımı ayar direnci  
- C1, C4, C5, C7 → Filtreleme kondansatörleri  
- LED1 (RED), LED2 (GREEN) → Şarj/Dolu göstergeleri  
- USB Micro-B (giriş), USB-A (çıkış)  

---

## ⚡ Çalışma Prensibi
1. **Şarj Modu:** USB’den gelen 5V → TP4056 → Li-Ion pili şarj eder.  
2. **Boost Modu:** Pil voltajı (3.0–4.2V) → TPS61040 boost devresi → 5V’a yükseltilir.  
3. **Koruma Devresi:** Schottky diyot ters akımı engeller, zener diyot aşırı gerilime karşı çıkışı korur.  

---

## 📊 Test ve Ölçümler
- **Giriş Voltajı:** 5V  
- **Pil Voltajı:** 3.0–4.2V  
- **Çıkış Voltajı:** 5V sabit  
- **LED Durumları:**  
  - 🔴 Kırmızı LED → Şarj aktif  
  - 🟢 Yeşil LED → Şarj tamamlandı  

---

## 🚀 Kullanım Alanları
- Powerbank devreleri  
- Taşınabilir sensör sistemleri  
- Küçük gömülü sistemler  
- IoT cihaz prototipleri  

---

## 📌 Notlar
- Şarj akımı **Rprog (R1)** direnci ile ayarlanır. (Örn: 1.2kΩ → ~1A)  
- TP4056’in **ısı dağılımına** dikkat edilmeli. PCB’de yeterli bakır yüzeyi önerilir.  
- Çıkış akımı TPS61040 kapasitesine bağlıdır (~200–400mA).  
