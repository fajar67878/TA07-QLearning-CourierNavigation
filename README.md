# Tugas Akhir 07 (TA-07): Implementasi Q-Learning untuk Skenario RL Diskrit

**Mata Praktikum:** Pembelajaran Mesin  
**Dosen Pengampu:** Mohammad Bayu Anggara, S.Kom., M.Kom.  
**Nama:** Muhammad Fajar Ramdani  
**NIM:** 301240036  

---

## Deskripsi Skenario
Proyek ini mengimplementasikan algoritma **Q-Learning** berbasis tabel (*tabular Q-Learning*) pada lingkungan simulasi diskrit **Optimasi Rute Kurir Paket (Grid World 5x5)**. Agen kurir dilatih untuk menemukan rute terpendek dari gudang (`START`) menuju lokasi pelanggan (`GOAL`) sambil menghindari zona kemacetan/blokade jalan (`MACET`).

## Definisi Elemen Reinforcement Learning ($S, A, R$)
* **State Space ($S$):** 25 posisi koordinat diskrit pada grid $5 \times 5$ (indeks `0` hingga `24`).
* **Action Space ($A$):** 4 aksi pergerakan deterministik (`0: Atas`, `1: Bawah`, `2: Kiri`, `3: Kanan`).
* **Reward Function ($R$):**
  * `+100` : Berhasil mencapai lokasi tujuan (`GOAL` pada koordinat `(4,4)`).
  * `-50` : Masuk ke area kemacetan/blokade jalan (`MACET`), episode langsung berakhir (*terminated*).
  * `-1` : Setiap langkah di jalan normal (mendorong agen mencari rute tercepat).
  * `-5` : Menabrak batas tepi kota (posisi agen tetap).

## Struktur Repositori
* `TA07_301240036_MuhammadFajarRamdani.ipynb` — Notebook Google Colab yang mencakup:
  1. Pembuatan lingkungan simulasi kustom (`CourierGridEnv`).
  2. Pelatihan algoritma Q-Learning menggunakan Persamaan Bellman dan strategi $\epsilon$-greedy.
  3. Visualisasi Kurva Pembelajaran (*Moving Average* 50 episode).
  4. Visualisasi Peta Kebijakan Optimal (*Optimal Policy*).
  5. Eksperimen perbandingan hiperparameter *Discount Factor* ($\gamma = 0.95$ vs $\gamma = 0.05$).

## Cara Menjalankan
1. Buka file `.ipynb` melalui **Google Colab** atau **Jupyter Notebook**.
2. Jalankan seluruh sel secara berurutan (**Runtime > Run all**).
