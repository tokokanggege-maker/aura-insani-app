# Aura Insani Mobile App + HGG Booking 5.1.0

Paket ini mengubah sistem HGG Booking WordPress menjadi backend API untuk aplikasi Android native.

## Yang sudah disesuaikan
- Login pasien menggunakan nomor WhatsApp + password.
- Registrasi pasien.
- Dashboard pasien.
- Riwayat booking.
- Booking konsultasi.
- Slot jam realtime dari WordPress.
- Pencegahan double booking di server.
- Status booking.
- Dashboard admin dari aplikasi.
- Admin dapat mengubah status booking.
- Data pasien tersedia melalui API admin.
- Token aplikasi Bearer 30 hari, disimpan sebagai hash di database.
- WhatsApp admin default: 6288973651329 (088973651329).
- Logo Aura Insani dibawa ke aplikasi.

## Instal plugin
1. Backup WordPress.
2. Nonaktifkan plugin HGG Booking lama.
3. Upload `hgg-booking-v5.1.0-mobile-api.zip` sebagai plugin WordPress.
4. Aktifkan plugin.
5. Buka Pengaturan > Permalink dan klik Simpan jika endpoint REST belum bisa diakses.
6. Pastikan HTTPS aktif.

## Android
Project ada di folder `android/`.
API bawaan:
`https://pengobatan.aurainsani.com/wp-json/hgg/v1/`

Untuk build APK pada komputer yang memiliki Android Studio/SDK:
- buka folder `android/` di Android Studio
- Sync Gradle
- Build > Build APK(s)

## Catatan keamanan
Password tidak pernah dikirim atau disimpan oleh aplikasi selain melalui HTTPS ke endpoint login. Aplikasi menyimpan token sesi, bukan password. Token server berlaku 30 hari dan dapat dicabut saat logout.

## Endpoint utama
POST /auth/register
POST /auth/login
POST /auth/logout
GET /me
GET /slots?date=YYYY-MM-DD
GET /bookings
POST /bookings
GET /admin/stats
PATCH /admin/bookings/{id}
GET /admin/patients
GET /admin/settings
