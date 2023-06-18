# Problem 4

Anda diberi data pasangan (x1, x2) yang tidak berlabel seperti pada tabel berikut.
| Data # | x1 | x2 |
| --- | --- | --- |
| 1 | 1.14 | 2.11 |
| 2 | 1.90 | 0.97 |
| 3 | 3.17 | 4.96 |
| 4 | 5.02 | 3.02 |
| 5 | 1.76 | 0.84 |
| 6 | 2.32 | 1.63 |
| 7 | 2.25 | 3.47 |
| 8 | 5.74 | 3.84 |
| 9 | 4.71 | 3.60 |
| 10 | 2.31 | 2.09 |

Anda diminta melakukan clustering data tersebut dalam dua cluster menggunakan Gaussian mixture Models (GMM). Lakukan inisialisasi dua pusat cluster dengan memilih dua titik data yang ada pada tabel, inisialisasi prior probability tiap cluster = $0.5$, dan standar deviasi tiap cluster adalah setengah dari jarak antara kedua pusat tersebut

<ol type="a">
  <li>Dengan nilai inisialisasi di atas: (i) tuliskan persamaan GMM dan (ii) hitung nilai 
keanggotaan cluster untuk setiap titik data pada tabel</li>
  <li>Hitung Rand Index untuk evaluasi clustering dan tulis analisis Anda</li>
  <li>Gunakan algoritma EM untuk update parameter GMM (1 epoch). Tuliskan parameter 
setelah update. Anda boleh menggunakan perangkat lunak apa saja yang sesuai</li>
</ol>

**Solution**
-