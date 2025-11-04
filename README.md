<p align="center">
  <img src="https://readme-typing-svg.demolab.com?font=Fira+Code&size=22&pause=1000&color=00D1B2&center=true&vCenter=true&width=700&lines=Verified+Labs+Wallet+Generator;Multi-Chain+%7C+Secure+Output+v1.0" alt="Verified Labs Typing SVG" />
</p>

# 🧠 Wallet Generator Multi-Chain — Verified Labs

Script Python untuk **membuat banyak wallet crypto unik** (mnemonic / private key / address),  
kemudian **mengecek saldo di beberapa jaringan (Ethereum, BSC, Base)** secara paralel,  
dan **menyimpan wallet yang berisi saldo ke file `balance.csv`**.

---

## 🚀 Fitur Utama
✅ Generate wallet baru dengan mnemonic 12 kata  
✅ Cek saldo di banyak jaringan (multi-chain parallel)  
✅ Simpan wallet dengan saldo ke CSV otomatis  
✅ Hindari duplikasi address (selalu unik)  
✅ File disimpan aman dengan izin `chmod 600` (hanya bisa dibaca pemilik)  

---

## 🧩 Persiapan

### 1️⃣ Instal dependensi
```bash
pip install -r requirements.txt
```

### 2️⃣ Buat file `.env`
Contoh isi `.env`:
```env
RPC_ETH=https://mainnet.infura.io/v3/YOUR_API_KEY
RPC_BSC=https://bsc-dataseed.binance.org
RPC_BASE=https://mainnet.base.org
```

Kamu juga bisa ganti RPC sesuai kebutuhan (Infura, Alchemy, QuickNode, Ankr, dll).

---

## ▶️ Cara Menjalankan
```bash
python3 wallet_gen_multi.py
```

Lalu ikuti prompt:
```
=== Wallet Generator Multi-Chain (unique-only, save funded to balance.csv) ===
Masukkan jumlah wallet yang ingin dibuat (unik): 100
RPC tersedia untuk chain: ethereum, bsc, base
Pilih chain yang ingin dicek (pisah koma) atau ENTER semua [ethereum, bsc, base]:
```

---

## 🧾 File Output

| File | Keterangan |
|------|-------------|
| `phrase.txt` | Mnemonic (12 kata) |
| `privatekey.txt` | Private key masing-masing wallet |
| `address.txt` | Alamat wallet |
| `balance.csv` | Wallet yang memiliki saldo |

---

## ⚠️ Keamanan
- Semua file memiliki permission `0o600` (hanya pemilik yang bisa baca/tulis).  
- **JANGAN bagikan** file `.txt` atau `.csv` ke siapapun.  
- Siapa pun yang memiliki mnemonic/private key bisa menguasai aset kamu.  

---

## 🧠 Contoh Output CLI

```
[1/100] 0x94F3D8... (balance: 0)
[2/100] 0x7e89b1... (funded: bsc:0.013 ETH) <-- disimpan di balance.csv
[3/100] 0x9a32ce... (balance: 0)
```

---

## 🧱 Catatan Teknis
- Mendukung Python ≥3.8  
- Parallel balance check menggunakan `ThreadPoolExecutor`  
- Waktu cek per 100 wallet ±5-10 detik (tergantung koneksi RPC)  
- Aman untuk dijalankan di server / VPS (no external API selain RPC)

---

> 🧩 Buatan oleh [**Verified Labs**](https://github.com/verifiedlabs)  
> _“Automate what’s boring, verify what matters.”_
