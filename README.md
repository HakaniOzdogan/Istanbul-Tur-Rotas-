# 🐜 İstanbul Tarihi Yarımada Rota Optimizasyonu (ACO)

![Python](https://img.shields.io/badge/Python-3.9%2B-blue)
![Streamlit](https://img.shields.io/badge/Streamlit-1.28-red)
![Algorithm](https://img.shields.io/badge/Algorithm-Ant%20Colony%20Optimization-green)
![API](https://img.shields.io/badge/Google-Maps%20API-yellow)
![License](https://img.shields.io/badge/License-MIT-lightgrey)

## 📖 Proje Özeti
Bu proje, **Gezgin Satıcı Problemi'nin (Traveling Salesman Problem - TSP)** gerçek hayat senaryosuna uygulanmış bir çözümüdür. İstanbul Tarihi Yarımada'da belirlenen 15 lokasyon için en kısa tur rotasını hesaplamak amacıyla biyolojik tabanlı sezgisel bir algoritma olan **Karınca Kolonisi Algoritması (Ant Colony Optimization - ACO)** kullanılmıştır.

Proje, gerçek trafik verilerini işlemek için **Google Maps Distance Matrix API**'sini kullanır ve sonuçları **Streamlit** üzerinden interaktif bir harita ve analiz grafikleriyle sunar.

## 🚀 Temel Özellikler
- **Hibrit Mesafe Hesaplama:** Google Maps API (Sürüş Modu) ve Haversine (Kuş Uçuşu - Yedekleme) entegrasyonu.
- **Dinamik Parametre Yönetimi:** ACO parametrelerinin ($\alpha, \beta, \rho$) kullanıcı arayüzünden anlık manipülasyonu.
- **Görselleştirme:** Folium tabanlı interaktif harita üzerinde rota çizimi ve yakınsama (convergence) grafikleri.
- **Modüler Mimari:** Clean Code prensiplerine uygun, katmanlı dosya yapısı (`core`, `data`, `visual`).
- **Güvenlik:** API anahtarlarının ortam değişkenleri (`secrets.toml`) üzerinden yönetimi.

## 📂 Proje Mimarisi
Proje, Sorumlulukların Ayrılığı (SoC) ilkesine göre yapılandırılmıştır:

```text
aco_istanbul_rotasi/
├── core/                   # Algoritma ve Mantık Katmanı
│   ├── ant_algorithm.py    # ACO Sınıfı ve Olasılık Hesaplamaları
│   ├── matrix_utils.py     # Google API ve Matris İşlemleri
│   └── haversine.py        # Yedek Mesafe Fonksiyonu (Vektörel)
├── data/                   # Veri Katmanı
│   └── coordinates.py      # Lokasyon Koordinat Verileri
├── .streamlit/             # Konfigürasyon
│   └── secrets.toml        # API Key (Git'e dahil edilmez!)
├── main.py                 # Sunum Katmanı (Streamlit UI)
├── requirements.txt        # Bağımlılıklar
└── README.md               # Proje Dokümantasyonu
