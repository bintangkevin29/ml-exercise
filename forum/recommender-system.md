## Forum Session 10 Subject Machine Learning (Recommender System)

Berikut tabel berisi daftar Film, dan kita akan menentukan rekomendasi berdasarkan pendekatan Content-Based Reccomendation System

| Movie Name         | User Rating | Genre                               |
| ------------------ | ----------- | ----------------------------------- |
| Batman v Superman  | 2           | Adventure, Superhero                |
| Guardian of Galaxy | 10          | Comedy, Adventure, Superhero, Scifi |
| Captain America    | 8           | Comedy, Superhero                   |

### Solusi

1. Pertama, akan kita buat tabel matrix dengan sumbu X berisi Genre, dan sumbu Y berisi nama Film, dengan data nilai 1 jika Genre nya cocok dan 0 jika sebaliknya.

   | Movie Name             | Adventure | Superhero | Comedy | Scifi |
   | ---------------------- | --------- | --------- | ------ | ----- |
   | Batman v Superman      | 1         | 1         | 0      | 0     |
   | Guardian of the Galaxy | 1         | 1         | 1      | 1     |
   | Captain America        | 0         | 1         | 1      | 0     |

2. Sekarang semua nilai 1 akan di kali dengan `User Rating` dari masing-masing film. Akan kita buat tabel baru dan kita beri nama `Weighted Genre Matrix`

   | Movie Name         | Adventure | Superhero | Comedy | Scifi |
   | ------------------ | --------- | --------- | ------ | ----- |
   | Batman v Superman  | 2         | 2         | 0      | 0     |
   | Guardian of Galaxy | 10        | 10        | 10     | 10    |
   | Captain America    | 0         | 8         | 8      | 0     |

3. Sekarang kita akan membuat sebuah tabel untuk menampung total nilai semua genre dari tabel `Weighted Genre Matrix`

   | Genre     | Value |
   | --------- | ----- |
   | Adventure | 12    |
   | Superhero | 20    |
   | Comedy    | 18    |
   | Scifi     | 10    |

4. Tabel kita normalisasi dengan membagi semua nilai dengan total nilai semua genre yaitu $12+20+18+10=60$. Tabel ini kita beri nama tabel `User Profile Table`

   | Genre     | Normalized Value |
   | --------- | ---------------- |
   | Adventure | 0.2              |
   | Superhero | 0.333            |
   | Comedy    | 0.3              |
   | Scifi     | 0.167            |

5. Setelah itu, kita akan fokus ke 3 film kandidat rekomendasi. Kita buatkan pula tabel matriks nya.

   | Movie Name                  | Adventure | Superhero | Comedy | Scifi |
   | --------------------------- | --------- | --------- | ------ | ----- |
   | Hitchiker's Guide to Galaxy | 1         | 0         | 1      | 1     |
   | Batman Begin                | 0         | 1         | 0      | 0     |
   | Spiderman                   | 0         | 1         | 1      | 0     |

6. Kita buatkan juga tabel `Weighted Genre Matrix` nya, tapi karena film-film ini tidak punya user rating, nilai 1 nya akan dikali dengan nilai dari `User Profile Table`

   | Movie Name                  | Adventure | Superhero | Comedy | Scifi |
   | --------------------------- | --------- | --------- | ------ | ----- |
   | Hitchiker's Guide to Galaxy | 0.2       | 0         | 0.3    | 0.167 |
   | Batman Begin                | 0         | 0.333     | 0      | 0     |
   | Spiderman                   | 0         | 0.333     | 0.3    | 0     |

7. Kita Hitung `Weighted Average` dari tiap genre dan kita normalisasi agar skala nya menjadi 0 sampai 10
   | Movie Name | Weighted Average | Normalized Weighted Average |
   |-------------------------------|---------------------|-----------------------------------|
   | **Hitchiker's Guide to Galaxy** | 0.667 | **6.67** |
   | Batman Begin | 0.333 | 3.33 |
   | Spiderman | 0.633 | 6.33 |

8. Berdasarkan nilai diatas, maka rekomendasi Film yang terpilih dari antara ketiga kandidat adalah film **`Hitchiker's Guide to Galaxy`**