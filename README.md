# STM32_UART_GPIO_Control# 
STM32 UART ile GPIO Kontrol Projesi

Bu proje, bir STM32 mikrodenetleyicisi kullanılarak bilgisayardan gönderilen UART mesajlarına göre iki adet GPIO pininin (LED) kontrol edilmesini sağlar.

## Proje Detayları
- **Kullanılan Kart:** STM32F103C8 (Blue Pill)
- **Kütüphane:** STM32Cube HAL (Hardware Abstraction Layer)
- **Haberleşme:** UART1 (Baud Rate: 9600, 8-bit, No Parity)
- **Kontrol Pinleri:** PA0 (1. Pin), PA1 (2. Pin)

## Mikrodenetleyici Seçimi
Bu projede **STM32F103C8** tercih edilmiştir. Tercih nedenleri:
* Proteus simülasyon ortamında en kararlı çalışan modellerden biri olması.
* ARM Cortex-M3 mimarisi ile yüksek hızda GPIO ve UART işlemleri yapabilmesi.
* Geniş topluluk desteği ve HAL kütüphanesi ile uyumu.

## Komut Yapısı ve Senaryo
Bilgisayardan (Terminal üzerinden) gönderilen 2 karakterlik mesajlar şu şekilde işlenir:
- **0:** Karşılık gelen pini **LOW** yapar.
- **1:** Karşılık gelen pini **HIGH** yapar.
- **2:** Karşılık gelen pini **TOGGLE** (durum değiştirme) yapar.

**Örnek:** - `11`: Her iki pini HIGH yapar.
- `10`: 1. Pin HIGH, 2. Pin LOW olur.
- `21`: 1. Pin durum değiştirir, 2. Pin HIGH olur.

## Kurulum ve Simülasyon
1. Kodlar STM32CubeIDE üzerinden derlenmiş ve Proteus ortamında simüle edilmiştir.
2. UART mesajları için "Virtual Terminal" bileşeni kullanılmıştır.
