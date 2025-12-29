# 🛡️ Quantum-Safe Edge Computing: Teknik Analiz

Kuantum bilgisayarların Shor algoritması gibi yöntemlerle mevcut RSA ve ECC temelli kriptografiyi etkisiz hale getirme potansiyeli, uç bilişim (Edge Computing) dünyası için kritik bir tehdittir. Bu belgede, uç cihazlarda uygulanacak stratejiler ele alınmaktadır.

## 1. NIST PQC Algoritmaları Seçimi

Uç cihazlar genellikle kısıtlı kaynaklara (CPU, RAM) sahip olduğu için her algoritma uygun değildir.

| Algoritma | Katman | Uç Cihaz Uygunluğu |
| :--- | :--- | :--- |
| **CRYSTALS-Kyber** | Anahtar Mekanizması (KEM) | ⭐⭐⭐⭐⭐ (Hızlı ve düşük bant genişliği) |
| **CRYSTALS-Dilithium** | Dijital İmza | ⭐⭐⭐⭐ (Stabil ancak büyük imza boyutu) |
| **Falcon** | Dijital İmza | ⭐⭐⭐ (Hızlı imzalama, karmaşık uygulama) |
| **Sphincs+** | Dijital İmza | ⭐⭐ (Yavaş imzalama, yüksek güvenlik) |

## 2. Hibrit Modeller

Tamamen PQC'ye geçmek yerine, mevcut klasik kriptografi ile PQC'nin birleştirildiği **Hibrit Modeller** önerilmektedir. 
- **Mantık:** Klasik katman (örneğin ECDH) kırılsa bile PQC katmanı veriyi korumaya devam eder.

## 3. Donanım Hızlandırma

Uç cihazlarda PQC performansını artırmak için:
- **FPGA Tabanlı Hızlandırma:** Kyber'in NTT (Number Theoretic Transform) işlemlerinin donanımda yapılması.
- **ARMv8 Crypto Extensions:** ARM işlemciler için özelleştirilmiş PQC kütüphanelerinin kullanımı.

---

> [!IMPORTANT]
> Harvest Now, Decrypt Later (Şimdi Topla, Sonra Çöz) saldırılarına karşı, verilerin bugünden kuantum-güvenli hale getirilmesi hayati önem taşır.
