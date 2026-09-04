# Warehouse Inventory Monitoring

## Project Overview

Project ini merupakan simulasi **Warehouse Inventory Management System (WMS)** menggunakan data operasional gudang FMCG selama periode Januari–Juni 2026. Analisis dilakukan untuk memantau pergerakan stok, mengidentifikasi kondisi overstock dan risiko stockout, serta mendukung pengambilan keputusan terkait pengendalian persediaan.

Dataset terdiri dari **200 SKU**, 1.500 transaksi barang masuk, dan 2.500 transaksi barang keluar yang diolah menggunakan Python dan Microsoft Excel hingga menghasilkan dashboard monitoring inventaris.

## Tools

* **Python (Pandas, NumPy)** — data inspection, cleaning, aggregation, dan analisis
* **Microsoft Excel** — data preparation, formula, Pivot Table, Slicer, dan dashboard
* **Matplotlib & Seaborn** — exploratory data analysis

## Business Problem

Pengelolaan persediaan menunjukkan ketidakseimbangan antara stok masuk dan stok keluar. Sebagian besar SKU mengalami **overstock**, sementara beberapa SKU berada di bawah Reorder Point sehingga berisiko mengalami stockout.

Diperlukan sistem monitoring yang dapat memberikan informasi kondisi persediaan secara lebih terstruktur untuk mendukung keputusan replenishment dan pengendalian stok.

## Objectives

* Menganalisis pergerakan inventaris selama Januari–Juni 2026.
* Mengidentifikasi SKU dengan kondisi **Safe Stock, Reorder Required, dan Overstock**.
* Memantau stok masuk, stok keluar, dan stok tersedia.
* Mengidentifikasi produk dengan level stok terendah.
* Menyediakan dashboard untuk mendukung monitoring dan pengambilan keputusan inventaris.

## Dataset

| Data             |            Jumlah |
| ---------------- | ----------------: |
| SKU              |               200 |
| Barang Masuk     |   1,500 transaksi |
| Barang Keluar    |   2,500 transaksi |
| Periode          | Januari–Juni 2026 |
| Total Received   |      130,900 unit |
| Total Dispatched |       64,027 unit |

Dataset terdiri dari beberapa sheet utama:

* `Master Barang` — informasi SKU, kategori, supplier, harga, dan parameter stok.
* `Stok Awal` — saldo awal inventaris.
* `Barang_Masuk` — transaksi penerimaan barang.
* `Barang_Keluar` — transaksi pengeluaran barang.
* `Data_Transaksi` — konsolidasi transaksi inbound dan outbound.
* `Data_Preparation` — hasil pengolahan data dan KPI.
* `Dashboard` — visualisasi monitoring inventaris.

## Data Preparation

Tahapan pengolahan data meliputi:

1. Memeriksa struktur dan kelengkapan data.
2. Menyesuaikan tipe data dan format tanggal transaksi.
3. Menggabungkan data stok awal, barang masuk, dan barang keluar.
4. Menghitung stok tersedia per SKU.
5. Mengklasifikasikan status inventaris berdasarkan parameter stok.
6. Melakukan agregasi bulanan untuk melihat perkembangan ketersediaan stok.

### Stock Available

$$
Stock\ Available = Beginning\ Stock + Qty\ Received - Qty\ Dispatched
$$

## Exploratory Data Analysis

Analisis eksplorasi dilakukan untuk memahami kondisi dan pola persediaan, meliputi:

* Perbandingan volume Inbound dan Outbound.
* Distribusi status stok berdasarkan SKU.
* Identifikasi Bottom 10 Stock.
* Analisis ketersediaan stok bulanan.
* Identifikasi SKU yang membutuhkan replenishment.

## Dashboard

Dashboard dirancang untuk memberikan monitoring inventaris secara ringkas dan interaktif.

### KPI Monitoring

* **Total Received:** 130,900 unit
* **Total Dispatched:** 64,027 unit
* **Total Available:** 191,381 unit
* **Total SKU:** 200

### Stock Performance

| Status           | Jumlah SKU |
| ---------------- | ---------: |
| Safe Stock       |         66 |
| Reorder Required |          2 |
| Overstock        |        132 |

Dashboard mencakup:

* Stock Performance Overview
* Bottom 10 Stock Monitoring
* Monthly Available Stock Trend
* Product & Category Filter
* Stock Status Monitoring

## Key Insights

* **66% SKU mengalami overstock**, dengan 132 dari 200 SKU berada di atas batas maksimum stok.
* Terdapat **2 SKU yang membutuhkan replenishment**, yaitu `DAR015` dan `INS003`.
* Total barang masuk mencapai **130,900 unit**, sedangkan barang keluar sebesar **64,027 unit**, menunjukkan selisih inbound dan outbound sebesar **66,873 unit**.
* Ketersediaan stok menunjukkan tren peningkatan selama periode analisis, yang mengindikasikan adanya akumulasi persediaan di gudang.

## Recommendations

* Melakukan evaluasi kuantitas pembelian pada SKU dengan status overstock.
* Meninjau kembali Reorder Point dan Safety Stock berdasarkan pola permintaan.
* Memprioritaskan replenishment untuk SKU yang berada di bawah Reorder Point.
* Mengelompokkan SKU berdasarkan tingkat pergerakan untuk mendukung class-based storage.
* Melakukan monitoring stok secara berkala menggunakan dashboard.

## Project Result

Project ini menghasilkan sistem monitoring inventaris berbasis Excel yang mampu memberikan informasi mengenai **stok tersedia, pergerakan barang, status persediaan, SKU kritis, dan tren ketersediaan stok**.

Hasil analisis dapat digunakan sebagai dasar untuk mengevaluasi kebijakan replenishment dan mengurangi ketidakseimbangan persediaan di gudang.
