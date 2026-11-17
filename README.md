# TemanKRL Station Data

Data stasiun yang dipakai aplikasi Android **TemanKRL**, pengingat stasiun
tujuan untuk Commuter Line Jabodetabek. Repositori ini menyediakan database
turunan secara terbuka, sesuai kewajiban share-alike
[ODbL 1.0](https://opendatacommons.org/licenses/odbl/1-0/).

| | |
|---|---|
| Versi data | **1.0.0** (sama persis dengan yang dibundel di aplikasi TemanKRL 1.2.0) |
| Cakupan | Lin Bogor, Lin Tangerang, Lin Rangkasbitung, 55 stasiun, 6 pola perjalanan |
| Lisensi | ODbL 1.0, lihat [LICENSE.md](LICENSE.md) |
| Sumber utama | [Commute Data Platform](https://data.commute.shiorilabs.id/docs) (Shiori Labs), ODbL 1.0 |

## Isi `masterdata/`

| File | Isi |
|---|---|
| `metadata.json` | Versi, cakupan, status verifikasi, riwayat perubahan, batasan |
| `stations.json` | Stasiun: ID, kode, nama, koordinat |
| `railway_lines.json` | Lintas KRL |
| `service_patterns.json` | Pola perjalanan per arah |
| `service_pattern_stops.json` | Urutan stasiun per pola |
| `data_sources.json` | Sumber data dan status verifikasinya |
| `README.md` | Catatan perubahan dataset |

## Atribusi

> Data stasiun dari Commute Data Platform (Shiori Labs), dilisensikan di bawah
> Open Database License (ODbL) 1.0, diolah oleh TemanKRL.

## Catatan

- Status "terverifikasi" berarti diterima pemilik aplikasi setelah uji
  lapangan. Belum ada cek silang dengan sumber resmi operator. Lihat
  `limitations` di `metadata.json`.
- TemanKRL adalah aplikasi independen dan tidak berafiliasi dengan
  PT Kereta Commuter Indonesia (KAI Commuter) atau PT Kereta Api Indonesia
  (Persero).
