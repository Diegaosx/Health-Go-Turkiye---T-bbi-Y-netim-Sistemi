# 🏥 Health Go Türkiye - Tıbbi Yönetim Sistemi

[![Vercel'de Dağıtıldı](https://img.shields.io/badge/Deployed%20on-Vercel-black?style=for-the-badge&logo=vercel)](https://vercel.com/diegaosxs-projects/v0-fitnessbookingapp3)
[![İle Oluşturuldu v0](https://img.shields.io/badge/Built%20with-v0.dev-black?style=for-the-badge)](https://v0.dev/chat/projects/H6UTs6rk1h1)
[![Next.js](https://img.shields.io/badge/Next.js-14-black?style=for-the-badge&logo=next.js)](https://nextjs.org/)
[![TypeScrip t](https://img.shields.io/badge/TypeScript-5-blue?style=for-the-badge&logo=typescript)](https://www.typescriptlang.org/)
[![Supabase](https://img.shields.io/badge/Supabase-Database-green?style=for-the-badge&logo=supabase)](https://supabase.com/)

## 📋 Genel Bakış

**Health Go Türkiye**, uluslararası hastalara çok dilli bir deneyim ve ameliyat öncesi ve sonrası tıbbi izleme için özel özellikler sunmak üzere tasarlanmış, saç tedavileri konusunda uzmanlaşmış kapsamlı bir tıbbi yönetim platformudur.

### 🌟 Temel Özellikler

- 🌍 **Çok Dilli Sistem** - 10 dil desteği
- 👨‍⚕️ **Tıbbi Kontrol Paneli** - Eksiksiz hasta ve tedavi yönetimi
- 👤 **Hasta Portalı** - Kişiselleştirilmiş tedavi takibi
- 📱 **Duyarlı** - Web ve mobil için optimize edilmiş (Capacitor)
- 🔒 **Güvenli** - Güçlü kimlik doğrulama ve tıbbi veri koruması
- 🔗 **Bitrix24 Entegrasyonu** - Otomatik CRM
- ☁️ **Bulut Depolama** - Fotoğraflar ve belgeler için Cloudflare R2
- 🔔 **Bildirim Sistemi** - Firebase Cloud Messaging (FCM) aracılığıyla çok dilli ve anlık bildirimler

## 🔥 Firebase Cloud Messaging (FCM) Yapılandırması

### 📋 Ön Koşullar

Ortamı ayarlamadan önce Değişkenler için bir Firebase projesi oluşturmanız ve yapılandırmanız gerekir:

### 🚀 1. Adım: Bir Firebase Projesi Oluşturun

1. **Firebase Konsoluna Erişin:**
- [https://console.firebase.google.com](https://console.firebase.google.com) adresine gidin
- Google hesabınızla oturum açın

2. **Yeni Proje Oluşturun:**
- "Proje Ekle"ye tıklayın
- Proje adı: `health-go-turkiye` (veya istediğiniz bir ad)
- Şartları kabul edin ve devam edin
- Google Analytics'i **Devre Dışı Bırakın** (FCM için gerekli değildir)
- "Proje Oluştur"a tıklayın

### 🌐 2. Adım: Web Uygulamasını Yapılandırın

1. **Web Uygulaması Ekleme:**
- Proje panosunda `</>` simgesine tıklayın
- Uygulama adı: `Health Go Turkiye Web`
- "Firebase Hosting'i de yapılandır"ı **İşaretleyin**
- "Kaydol"a tıklayın "uygulama"

2. **Yapılandırmayı Kopyala:**
\`\`\`javascript
// Şuna benzer bir şey alacaksınız:
const firebaseConfig = {
apiKey: "AIzaSyC...",
authDomain: "health-go-turkiye.firebaseapp.com",
projectId: "health-go-turkiye",
storageBucket: "health-go-turkiye.appspot.com",
messagingSenderId: "123456789012",
appId: "1:123456789012:web:abcdef123456"
};
\`\`\`

### 📱 3. Adım: Bulut Mesajlaşma'yı Etkinleştirin

1. **Bulut Mesajlaşma'ya Erişim:**
- Yan menüden "Mesajlaşma"ya gidin
- "Başlat"a tıklayın

2. **VAPID Anahtarı Oluşturun:**
- "Proje Ayarları"na (dişli simgesi) gidin
- "Bulut Mesajlaşma" sekmesi
- "Web Yapılandırması" bölümünde "Anahtar Çifti Oluştur"a tıklayın
- **Oluşturulan VAPID anahtarını kopyalayın**

### 🔑 4. Adım: Sunucu Anahtarını Alın

1. **Ayarlara Erişim:**
- Hâlâ "Proje Ayarları"ndayken
- "Bulut Mesajlaşma" sekmesi

2. **Sunucu Anahtarını Kopyala:**
- "Bulut Mesajlaşma API'si (Eski)" bölümünde
- **"Sunucu Anahtarını" kopyalayın**
- ⚠️ **Önemli:** Bu anahtar Gizli, ön uçta ifşa etmeyin.

### 📋 5. Adım: Ortam Değişkenlerini Yapılandırın

Şimdi `.env.local` ve Vercel'de aşağıdaki değişkenleri yapılandırın:

\`\`\`env
# Firebase Yapılandırması
FIREBASE_VAPID_KEY=your-firebase-vapid-key
FIREBASE_SERVER_KEY=your-firebase-server-key

# Ön Uç Firebase Yapılandırması (konsoldan edinilir) Firebase)
NEXT_PUBLIC_FIREBASE_API_KEY=your-api-key
NEXT_PUBLIC_FIREBASE_AUTH_DOMAIN=your-project.firebaseapp.com
NEXT_PUBLIC_FIREBASE_PROJECT_ID=your-project-id
NEXT_PUBLIC_FIREBASE_STORAGE_BUCKET=your-project.appspot.com
NEXT_PUBLIC_FIREBASE_MESSAGING_SENDER_ID=your-sender-id
NEXT_PUBLIC_FIREBASE_APP_ID=your-app-id
\`\`\`

### 📱 6. Adım: Mobil Cihazlar İçin Yapılandırma (Capacitor)

#### Android İçin:

1. **Android Uygulaması Ekle:**
- Firebase konsolunda Android simgesine tıklayın
- Paket adı: `com.healthgoturkiye.app`
- Uygulama takma adı: `Health Go Türkiye Android`
- SHA-1: (FCM için isteğe bağlı)

2. **google-services.json dosyasını indirin:**
- `google-services.json` dosyasını indirin
- `android/app/google-services.json` dizinine yerleştirin

#### iOS için:

1. **iOS Uygulaması Ekle:**
- Firebase konsolunda iOS simgesine tıklayın
- Paket Kimliği: `com.healthgoturkiye.app`
- Uygulama takma adı: `Health Go Türkiye iOS`

2. **GoogleService-Info.plist dosyasını indirin:**
- `GoogleService-Info.plist` dosyasını indirin
- `ios/App/App/GoogleService-Info.plist` dizinine yerleştirin

### 🔧 7. Adım: Capacitor'ı Yapılandırın

Güncelleme `capacitor.config.ts`:

\`\`\`typescript
içe aktar { CapacitorConf
