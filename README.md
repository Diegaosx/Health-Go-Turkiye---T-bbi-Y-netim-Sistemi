# Health-Go-Turkiye---T-bbi-Y-netim-Sistemi
# 🏥 Health Go Turkiye - Tıbbi Yönetim Sistemi

[![Vercel Üzerine Dağıtıldı](https://img.shields.io/badge/Vercel%20Üzerine%20Dağıtıldı-Vercel-black?style=for-the-badge&logo=vercel)](https://vercel.com/diegaosxs-projects/v0-fitnessbookingapp3)
[![v0 ile oluşturuldu](https://img.shields.io/badge/v0.dev%20ile%20Oluşturuldu-black?style=for-the-badge)](https://v0.dev/chat/projects/H6UTs6rk1h1)
[![Next.js](https://img.shields.io/badge/Next.js-14-black?style=for-the-badge&logo=next.js)](https://nextjs.org/)
[![TypeScript](https://img.shields.io/badge/TypeScript-5-blue?style=for-the-badge&logo=typescript)](https://www.typescriptlang.org/)
[![Supabase](https://img.shields.io/badge/Supabase-Veritabanı-green?style=for-the-badge&logo=supabase)](https://supabase.com/)

## 📋 Genel Bakış

**Health Go Turkiye**, uluslararası hastalar için çok dilli bir deneyim ve cerrahi öncesi ve sonrası tıbbi takip için özel işlevler sunmak üzere geliştirilmiş, saç tedavilerine özel kapsamlı bir tıbbi yönetim platformudur.

### 🌟 Temel Özellikler

- 🌍 **Çok Dilli Sistem** - 10 dil desteği
- 👨‍⚕️ **Tıbbi Panel** - Hastalar ve tedaviler için kapsamlı yönetim
- 👤 **Hasta Portalı** - Tedavinin kişiselleştirilmiş takibi
- 📱 **Mobil Uyumlu** - Web ve mobil (Capacitor) için optimize edilmiştir
- 🔒 **Güvenli** - Sağlam kimlik doğrulama ve tıbbi veri koruması
- 🔗 **Bitrix24 Entegrasyonu** - Otomatik CRM
- ☁️ **Bulut Depolama** - Fotoğraflar ve belgeler için Cloudflare R2
- 🔔 **Bildirim Sistemi** - Çok dilli ve Firebase Cloud Messaging (FCM) ile anlık bildirimler

## 🔥 Firebase Cloud Messaging (FCM) Yapılandırması

### 📋 Ön Gereksinimler

Ortam değişkenlerini yapılandırmadan önce, bir Firebase projesi oluşturmanız ve yapılandırmanız gerekir:

### 🚀 Adım 1: Firebase Projesi Oluşturma

1. **Firebase Konsoluna Erişin:**
   - [https://console.firebase.google.com](https://console.firebase.google.com) adresine gidin
   - Google hesabınızla giriş yapın

2. **Yeni Proje Oluşturun:**
   - "Proje ekle" seçeneğine tıklayın
   - Proje adı: `health-go-turkiye` (veya tercih ettiğiniz ad)
   - Şartları kabul edin ve devam edin
   - **Google Analytics'i devre dışı bırakın** (FCM için gerekli değildir)
   - "Projeyi oluştur" seçeneğine tıklayın

### 🌐 Adım 2: Web Uygulamasını Yapılandırma

1. **Web Uygulaması Ekleme:**
   - Proje panosunda `</>` simgesine tıklayın
   - Uygulama adı: `Health Go Turkiye Web`
   - **Firebase Hosting'i de yapılandır** seçeneğini işaretleyin
   - "Uygulamayı kaydet" seçeneğine tıklayın

2. **Yapılandırmayı Kopyalayın:**
   ```javascript
   // Şuna benzer bir yapılandırma alacaksınız:
   const firebaseConfig = {
     apiKey: "AIzaSyC...",
     authDomain: "health-go-turkiye.firebaseapp.com",
     projectId: "health-go-turkiye",
     storageBucket: "health-go-turkiye.appspot.com",
     messagingSenderId: "123456789012",
     appId: "1:123456789012:web:abcdef123456"
   };

   📱 Adım 3: Cloud Messaging Etkinleştirme
Cloud Messaging'e Erişin:
Yan menüde "Messaging" (Mesajlaşma) bölümüne gidin
"Başla" seçeneğine tıklayın
VAPID Anahtarı Oluşturun:
"Proje ayarları" (dişli simgesi) bölümüne gidin
"Cloud Messaging" sekmesine geçin
"Web yapılandırması" bölümünde "Anahtar çifti oluştur" seçeneğine tıklayın
Oluşturulan VAPID anahtarını kopyalayın
🔑 Adım 4: Sunucu Anahtarını Alma
Ayarları Erişin:
Hâlâ "Proje ayarları" bölümündeyken
"Cloud Messaging" sekmesine geçin
Sunucu Anahtarını Kopyalayın:
"Cloud Messaging API (Eski)" bölümünde
"Sunucu anahtarını" kopyalayın
⚠️ Önemli: Bu anahtar gizlidir, frontend'de asla açığa çıkarmayın
📋 Adım 5: Ortam Değişkenlerini Yapılandırma
Şimdi aşağıdaki değişkenleri .env.local dosyanızda ve Vercel'de yapılandırın:

# Firebase Yapılandırması
FIREBASE_VAPID_KEY=sizin-firebase-vapid-anahtarınız
FIREBASE_SERVER_KEY=sizin-firebase-sunucu-anahtarınız

# Frontend Firebase Yapılandırması (Firebase konsolundan alınır)
NEXT_PUBLIC_FIREBASE_API_KEY=sizin-api-anahtarınız
NEXT_PUBLIC_FIREBASE_AUTH_DOMAIN=sizin-projeniz.firebaseapp.com
NEXT_PUBLIC_FIREBASE_PROJECT_ID=sizin-proje-idniz
NEXT_PUBLIC_FIREBASE_STORAGE_BUCKET=sizin-proje.appspot.com
NEXT_PUBLIC_FIREBASE_MESSAGING_SENDER_ID=sizin-gönderici-idniz
NEXT_PUBLIC_FIREBASE_APP_ID=sizin-app-idniz

📱 Adım 6: Mobil (Capacitor) için Yapılandırma
Android için:
Android Uygulaması Ekleme:
Firebase konsolunda Android simgesine tıklayın
Paket adı: com.healthgoturkiye.app
Uygulama takma adı: Health Go Turkiye Android
SHA-1: (FCM için isteğe bağlı)
google-services.json Dosyasını İndirin:
google-services.json dosyasını indirin
android/app/google-services.json yoluna yerleştirin
iOS için:
iOS Uygulaması Ekleme:
Firebase konsolunda iOS simgesine tıklayın
Demet kimliği: com.healthgoturkiye.app
Uygulama takma adı: Health Go Turkiye iOS
GoogleService-Info.plist Dosyasını İndirin:
GoogleService-Info.plist dosyasını indirin
ios/App/App/GoogleService-Info.plist yoluna yerleştirin
🔧 Adım 7: Capacitor Yapılandırması
capacitor.config.ts dosyasını güncelleyin:
import { CapacitorConfig } from '@capacitor/core';

const config: CapacitorConfig = {
  appId: 'com.healthgoturkiye.app',
  appName: 'Health Go Turkiye',
  webDir: 'out',
  server: {
    androidScheme: 'https'
  },
  plugins: {
    PushNotifications: {
      presentationOptions: ["badge", "sound", "alert"]
    },
    FirebaseMessaging: {
      presentationOptions: ["badge", "sound", "alert"]
    }
  }
};

export default config;

🔧 Adım 8: Yapılandırmayı Test Etme
Yerel Test:
npm run dev
# Tarayıcı konsolunu açın
# "Firebase başarıyla başlatıldı" mesajı görünmelidir
