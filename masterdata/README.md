# TemanKRL Master Data — 1.0.0

## Perubahan 1.0.0 (17 Nov 2026)
- Rilis produksi pertama: dataset ditandai **terverifikasi** oleh pemilik produk setelah uji lapangan (DECISIONS D-066).
- Isi stasiun, lintas, dan pola **identik** dengan 0.2.1-draft. Tidak ada cek silang resmi tambahan; batasan di `metadata.json` tetap berlaku.

## Riwayat: Draft 0.2.1
## Perubahan 0.2.1 (14 Nov 2026)
- Ditambahkan **Stasiun Jatake** (`KCI-JTK`, kode `JTK`) di Lin Rangkasbitung, antara Cicayur dan Parung Panjang:
  `KCI-SP-R-OUT` urutan 11, `KCI-SP-R-BACK` urutan 10; stasiun sesudahnya di kedua pola bergeser satu.
- Sumber: file tugas pemilik produk (kode, koordinat, posisi). Koordinat dicek silang dengan OpenStreetMap
  (way 631439998): selisih ±30 m, koordinat **tidak** diubah. Kode `JTK` belum terkonfirmasi sumber resmi.
  Status operasi: beroperasi 28 Jan 2026 (berita). Lihat `data_sources.json`.
- Tidak ada record stasiun lain yang diubah. Status dataset tetap DRAFT.

## Update dari file yang kamu upload
File berisi JSON response dengan 112 record stasiun. Data terpilih dicocokkan berdasarkan nama stasiun (dengan normalisasi ejaan) dan diambil `id`, `code`, `officialName`, `operator`, `lines`, `latitude`, `longitude`, serta `regionCode`.

## Hasil
- Stasiun terpilih: 55 (54 dari API + Jatake dari pemilik produk)
- Lin: 3
- Pola arah baseline: 6
- Baris urutan stasiun: 110
- Koordinat kosong: 0
- Kode stasiun duplikat: 0
- Koordinat di luar rentang: 0

## Cakupan
- Green Line / Lin Rangkasbitung: Tanah Abang ↔ Rangkasbitung
- Brown Line / Lin Tangerang: Duri ↔ Tangerang
- Red Line / Lin Bogor: Jakarta Kota ↔ Bogor
- Cabang Nambo tidak dimasukkan.

## Status dan batasan penting
(Catatan dari versi draft 0.2.1, sebelum D-066.) Dataset ini masih DRAFT. Koordinat dan kode sekarang terisi dari file API yang kamu berikan, tetapi belum diverifikasi silang dengan sumber resmi/independen. Jangan aktifkan GPS reminder produksi hanya berdasarkan file ini.

`service_patterns.json` dan `service_pattern_stops.json` berisi enam urutan dasar dua arah berdasarkan peta. Ini BUKAN inventaris semua pola berhenti operasional. Permintaan pola berhenti ALL membutuhkan data jadwal/perjalanan aktual per nomor perjalanan, arah, dan hari operasi.

## Catatan pencocokan
- Ejaan `Bojong Gede` pada peta dicocokkan dengan `Bojonggede` pada data API.
- `Kali Deres` pada peta dicocokkan dengan `Kalideres` pada data API.
- Station ID dan kode diambil dari record API; station display name mengikuti nama pada peta untuk konsistensi UI.
- `source_api_lines` disimpan sebagai metadata referensi, bukan satu-satunya penentu urutan perjalanan.

## File
- `stations.json`
- `railway_lines.json`
- `service_patterns.json`
- `service_pattern_stops.json`
- `data_sources.json`
- `metadata.json`

## Checklist sebelum production
1. Cross-check koordinat tiap stasiun terhadap sumber independen / survei.
2. Verifikasi nama resmi dan kode stasiun yang berlaku.
3. Verifikasi konektivitas/segmen lin dan titik interchange.
4. Dapatkan pola berhenti aktual per trip (bukan hanya lin), termasuk short-turn dan variasi hari operasi.
5. Validasi GPS radius, arah, dan progress di perangkat Android nyata.
6. Review lisensi sumber dan kewajiban atribusi sebelum distribusi.
