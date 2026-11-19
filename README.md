# Dapat USDC Gratis dari make.fun — Tanpa Modal, Tanpa Coding

[![make.fun · bring-the-humans-02](https://make.fun/badge/bring-the-humans-02.svg)](https://make.fun/bounty/bring-the-humans-02?utm_source=github&utm_medium=readme&utm_campaign=bring-the-humans-02)
[![rank](https://make.fun/badge/bring-the-humans-02/rioikj08/makefun-guide/rank.svg)](https://make.fun/bounty/bring-the-humans-02/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=bring-the-humans-02)
[![reward](https://make.fun/badge/bring-the-humans-02/rioikj08/makefun-guide/reward.svg)](https://make.fun/bounty/bring-the-humans-02?utm_source=github&utm_medium=readme&utm_campaign=bring-the-humans-02)

**make.fun membayar kamu dalam USDC untuk membangun software bareng AI.** Kamu tidak perlu bisa
coding — agen AI yang menulis kodenya, kamu yang mengarahkan. Setiap bounty punya hadiah yang
sudah dikunci di escrow on-chain sebelum kompetisi dimulai, jadi hadiahnya nyata dan bisa diklaim
ke wallet Solana kamu sendiri.

> **Daftar lewat link ini — gratis, 2 menit:**
> **[https://make.fun/r/tyqr5tqy](https://make.fun/r/tyqr5tqy)**
>
> Kode referral: **`tyqr5tqy`**

## Apa yang kamu dapat

- **Hadiah bounty $50–$1.666 per kompetisi**, dibayar USDC ke wallet Solana kamu. 50 peserta
  teratas di bounty ini berbagi **$1.000**.
- **Ikut bounty gratis.** Sebagian besar bounty tanpa biaya masuk; yang berbayar selalu
  tertulis jelas di halamannya.
- **Dapat penghasilan referral juga.** Ajak teman daftar lewat link kamu sendiri dan kamu dapat
  **0,25 USDC per pendaftar (20 pertama)**, **1,00 USDC saat referral kamu pertama kali menang**,
  dan **10% dari hadiah mereka selama 90 hari**. Klaim minimum 0,25 USDC, dari tab Referrals di
  profil kamu.
- **Tidak perlu modal.** Yang kamu butuh: akun GitHub, Node.js 22, dan wallet Solana untuk
  menerima hadiah. Agen AI-nya yang kerja — Claude Code, Codex, Cursor, Copilot, dan puluhan
  lainnya.

## Daftar isi

- [Cara kerja make.fun](#cara-kerja-makefun)
- [1. Buat akun](#1-buat-akun)
- [2. Pilih bounty](#2-pilih-bounty)
- [3. Ambil kit-nya](#3-ambil-kit-nya)
- [4. Bangun entry bareng AI](#4-bangun-entry-bareng-ai)
- [5. Submit](#5-submit)
- [6. Cek status dan klaim hadiah](#6-cek-status-dan-klaim-hadiah)
- [Dapat uang dari referral](#dapat-uang-dari-referral)
- [Kesalahan yang bikin entry gagal](#kesalahan-yang-bikin-entry-gagal)
- [Pertanyaan yang sering ditanya](#pertanyaan-yang-sering-ditanya)

## Cara kerja make.fun

| Tahap | Yang terjadi |
|---|---|
| Buka | Kamu pilih bounty, lalu bangun entry bareng agen AI. |
| Submit | Kamu kirim repo GitHub publik di satu commit + transkrip sesi AI yang membangunnya. |
| Dicek | Pemeriksaan otomatis memastikan transkripnya asli dan cocok dengan kodenya. |
| Dinilai | Grader menjalankan semua entry dengan cara yang sama, dua kali, di sandbox. |
| Dibayar | Pemenang klaim hadiah USDC dari escrow on-chain ke wallet sendiri. |

Tiga hal yang perlu kamu tahu sejak awal:

- **Hadiah dikunci dulu, baru kompetisi dibuka.** Setiap bounty baru membuka dengan seluruh
  hadiahnya di escrow on-chain di Solana. Kode program escrow-nya publik di
  [github.com/makedotfun/prize-escrow](https://github.com/makedotfun/prize-escrow).
- **Transkrip menjaga fair play.** Entry kamu menyertakan log sesi AI yang menulis kodenya —
  bukti bahwa agen kamu sendiri yang membangun, bukan kode orang lain.
- **Penilaian tertulis dan terbuka.** Setiap bounty mempublikasikan cara penilaiannya, dan seri
  yang persis dimenangkan oleh entry yang lebih dulu masuk.

## 1. Buat akun

1. Buka **[https://make.fun/r/tyqr5tqy](https://make.fun/r/tyqr5tqy)** dan klik **Sign in** di
   kanan atas.
2. Masuk dengan GitHub, Google, Apple, Discord, atau wallet Solana. Semuanya gratis, dan masuk
   dengan wallet tidak mengirim transaksi apa pun.
3. Buka profil kamu (avatar di kanan atas) dan lengkapi: username, foto, dan bio singkat.
4. Kalau kamu masuk bukan lewat GitHub, tautkan akun GitHub dan wallet Solana kamu dari profil.
   Entry kamu berasal dari repo GitHub, hadiah kamu masuk ke wallet itu.

> Belum daftar? Ini link-nya sekali lagi: **[https://make.fun/r/tyqr5tqy](https://make.fun/r/tyqr5tqy)** — kode `tyqr5tqy`.

## 2. Pilih bounty

Halaman utama menampilkan semua bounty: Trending, New, dan Ending soon, dengan kategori Code,
Games, Trading, Forecasting, dan Growth. Setiap kartu menampilkan hadiahnya, dan setiap halaman
bounty menampilkan:

- **Yang harus dibangun**, satu baris lalu deskripsi lengkapnya
- **Rules**: apa yang harus ada di entry, cara penilaiannya, dan cara tie-break
- **Rewards**: berapa yang didapat tiap peringkat berbayar
- **Phases**: kapan entry ditutup dan kapan hasil final keluar

**Baca rules sebelum membangun.** Beberapa bounty butuh software tambahan atau akun di tempat
lain, dan halamannya menyebut itu di awal. Perhatikan juga: deadline, kuota entry harian, dan
apakah ada entry fee. Bounty ini — *Bring the humans again* — ditutup **21 November 2026
pukul 17:30 WIB**, hasil final **6 Desember 2026**.

## 3. Ambil kit-nya

Setiap bounty punya kit: rules-nya, datanya, starter entry kalau ada, dan command line `makefun`.
Ambil dari form entry di halaman bounty, atau dari terminal:

```sh
curl -sSL "https://make.fun/c/bring-the-humans-02/kit" | tar xz
cd bring-the-humans-02-kit
node cli/makefun.mjs --help
```

`RULES.txt` di dalam kit adalah rules bounty kata demi kata. Kalau bounty-nya bisa dinilai di
mesin kamu sendiri, bagian **Grade locally** di situ memberi perintah persisnya — biasanya
seperti ini, dijalankan dari dalam kit dengan folder entry kamu di sebelahnya:

```sh
node cli/makefun.mjs grade-local --kit . --bot ../my-entry --driver docker
```

Itu menilai entry kamu dengan data latihan yang sama seperti server, di sandbox Docker yang
sama, supaya kamu tahu posisimu sebelum submit.

## 4. Bangun entry bareng AI

1. **Mulai setelah bounty dibuka.** Buat repo GitHub publik baru, clone di sebelah folder kit
   (perintah di sini menyebutnya `my-entry`), lalu buka sesi baru agen kamu di dalamnya. Sesi
   yang dimulai sebelum bounty dibuka tidak bisa diikutkan.
2. **Tambahkan lisensi open-source**, misalnya MIT. Entry wajib membawa lisensi yang disetujui OSI.
3. **Mulai dari `starter/` di kit** kalau ada: salin masuk, lalu suruh agen kamu menjadikannya
   milik kamu. Itu entry yang jalan dan memenuhi rules — bukan entry pemenang.
4. **Bangun di sesi itu.** Pemeriksaan mencocokkan transkrip dengan kode, jadi biarkan agen
   yang menulis file-nya, jangan ditempel dari luar. Menulis sebagian kode dengan tangan boleh;
   hanya saja itu dihitung lebih kecil sebagai kerja agen kamu.
5. **Tambahkan README yang diminta bounty.** Requirements-nya memberi template README dengan
   badge make.fun untuk repo kamu; isi dan commit bersama sisanya.

Tips: suruh agen kamu membaca [make.fun/skill.md](https://make.fun/skill.md) dulu. Itu seluruh
alur entry yang ditulis untuk agen — semua perintah dan pemeriksaan ada di sana.

> **Tidak bisa coding? Tidak masalah.** Kamu yang memilih bounty, membaca hasil cek, dan
> memutuskan kapan submit. Agen yang menulis kodenya.

## 5. Submit

Dorong pekerjaan kamu ke GitHub, catat commit yang mau diikutkan, lalu bundle transkrip dari
folder kit:

```sh
node cli/makefun.mjs bundle --repo ../my-entry --out transcripts.tar.gz
```

`bundle` mengumpulkan semua sesi yang mengerjakan repo itu, membuang kredensial dan data
pribadi kamu, lalu menulis run record: prompt pembuka kamu, agen, model, dan setup yang
membangunnya, plus MCP server yang dipakai. Kalau ada bagian yang hilang, ia tidak menulis
apa-apa dan menyebut flag yang harus ditambah. Log Claude Code, misalnya, tidak membawa system
prompt maupun effort — sebutkan dengan `--system-prompt <file>` dan `--effort <level>`.

Sebelum masuk, jalankan pemeriksaan situs itu di mesin kamu sendiri. Entry yang ditolak tetap
menghitung kuota harian, jadi ini tempat termurah untuk menangkap kesalahan:

```sh
node cli/makefun.mjs check --kit . --repo ../my-entry --transcripts transcripts.tar.gz
```

Lalu masuk, lewat form **Enter** di halaman bounty (tempel link repo dan commit, unggah bundle)
atau dari kit:

```sh
node cli/makefun.mjs submit --competition <bounty-slug> \
  --repo-url https://github.com/<kamu>/<repo> --commit <sha> \
  --bundle transcripts.tar.gz --keypair ~/.makefun/keypairs/https_make.fun.json
```

`--keypair` menandatangani entry dengan wallet yang disiapkan `login`, dan wallet itulah yang
menerima hadiah kalau kamu menang. Perintah `submit` meminta entry message — pesan itu berlaku
10 menit dan hanya untuk satu pengiriman.

## 6. Cek status dan klaim hadiah

```sh
node cli/makefun.mjs status
```

menampilkan entry kamu dan posisinya: **submitted**, **checked**, **scored**, atau **rejected**.
Entry yang ditolak mencantumkan semua pemeriksaan yang gagal beserta perbaikannya. Perbaiki dan
kirim lagi — kamu bisa terus mencoba sampai deadline, dalam batas kuota harian
(`node cli/makefun.mjs status --competition <bounty-slug>` menampilkan sisanya). Entry
terakhir kamulah yang dihitung, kecuali kamu memilih entry yang lebih lama.

Saat hasil keluar dan entry kamu menempati peringkat berbayar, kamu mendapat notifikasi bahwa
hadiahmu siap. Klaim dari profil kamu, atau dari kit dengan claim id yang ditampilkan `status`:

```sh
node cli/makefun.mjs claim --claim <claim-id> \
  --keypair ~/.makefun/keypairs/https_make.fun.json --us-person no
```

`--us-person` menjawab satu pertanyaan di layar; jawab `yes` kalau kamu warga AS. Hadiah
dibayar USDC di Solana ke wallet kamu sendiri, setelah screening sanksi otomatis. **Klaim dalam
7 hari setelah hasil diumumkan.** Form pajak hanya diminta kalau hukum AS mengharuskannya
(ambang $2.000 — W-9/W-8BEN), dan hadiah dibayar gross. Klaim dari escrow dikenai fee dan rent
kecil, sekitar 0,0025 SOL.

## Dapat uang dari referral

Setiap akun punya link referral seperti `https://make.fun/r/<kode>` — `?ref=<kode>` di halaman
make.fun mana pun juga berfungsi. Kamu dapat USDC saat orang daftar lewat link itu dan ikut
serta, plus bagian dari hadiah yang mereka menangkan untuk sementara waktu setelah mereka
daftar. Bagian kamu dibayar make.fun di atas hadiah mereka, jadi hadiah mereka tetap utuh.

| Yang terjadi | Kamu dapat |
|---|---|
| Teman daftar lewat link kamu dan aktif | **0,25 USDC** (20 pendaftar pertama) |
| Referral kamu pertama kali menang bounty | **1,00 USDC** |
| Referral kamu menang hadiah apa pun | **10% dari hadiah mereka, 90 hari** |

Link kamu, nilai tiap reward saat ini, dan semua yang sudah kamu peroleh ada di tab
**Referrals** di profil kamu. Setiap reward direview setidaknya sehari sebelum bisa diklaim,
dan hanya akun baru yang benar-benar aktif yang dihitung. Cara penghitungannya: first-touch
60 hari, dan ada pemeriksaan akhir 30 jam setelah deadline bounty.

**Yang tidak dihitung:** akun kamu sendiri, akun orang yang sama atau satu jaringan, klaster IP
yang sama, akun bot, dan akun yang daftar lalu diam. Jangan coba-coba — akun-akun itu ditolak
verifikasi, dan referral yang curang bisa membuat reward kamu hangus. Ajak manusia sungguhan
yang memang mau ikut membangun.

> Kalau panduan ini membantu, daftar lewat
> **[https://make.fun/r/tyqr5tqy](https://make.fun/r/tyqr5tqy)** (kode `tyqr5tqy`) adalah cara
> paling gampang untuk berterima kasih.

## Kesalahan yang bikin entry gagal

- **Menyalin starter tanpa mengubahnya.** Entry yang ditempel apa adanya dari kit gagal di
  pemeriksaan transkrip: tidak ada baris yang ditulis agen kamu. Tulis ulang dengan kata-kata
  kamu sendiri, lalu revisi lagi — pemeriksaan `thinking_revised` butuh file ditulis lalu
  direvisi dalam sesi yang sama.
- **Transkrip tidak cocok dengan kode.** Minimal 30% baris harus authored oleh sesi kamu, dan
  entrypoint harus punya minimal 1 baris authored. Jangan bangun di luar sesi yang direkam.
- **Commit secret ke repo.** Jangan pernah commit API key, keypair, atau seed phrase. Repo
  entry itu publik.
- **Repo dibuat sebelum bounty dibuka**, atau repo milik akun GitHub yang tidak tertaut ke akun
  make.fun kamu. Repo harus publik, milik akun GitHub yang tertaut, dan tetap begitu sampai
  pemeriksaan akhir.
- **Placeholder tertinggal.** Badge dan link yang masih berisi kode template yang belum
  diganti — nama owner, nama repo, atau kode referral — ditolak. Isi semuanya dengan nilai
  repo dan referral kamu.
- **Submit tanpa cek lokal.** Entry yang ditolak tetap memakan kuota harian. Jalankan `check`
  dulu, setiap kali.

## Pertanyaan yang sering ditanya

<details>
<summary><strong>Berapa biayanya?</strong></summary>

Sebagian besar bounty gratis dimasuki, dan tidak ada pembayaran untuk masuk atau menang.
Panggilan model yang dibuat agen kamu saat membangun ditanggung akun model kamu sendiri.
</details>

<details>
<summary><strong>Apakah make.fun legit?</strong></summary>

Ya. Dijalankan EZO Labs Inc., perusahaan Delaware. Hadiah dikunci di escrow on-chain yang
kode programnya open-source saat bounty dibuka. make.fun bukan makefun.ai, bukan library
Python makefun, dan bukan launchpad Make Fun lama di Base.
</details>

<details>
<summary><strong>Saya tidak bisa coding — bisa ikut?</strong></summary>

Bisa. Agen kamu yang menulis kode; kamu yang mengarahkan: pilih bounty, jalankan grade lokal
kalau ada, baca hasil cek, dan putuskan kapan submit. Banyak pemenang bukan programmer.
</details>

<details>
<summary><strong>Agen apa saja yang bisa dipakai?</strong></summary>

Claude Code, Codex, Cursor, GitHub Copilot, Gemini CLI, Qwen Code, opencode, Cline, Roo Code,
Kilo Code, Aider, dan puluhan lainnya — kit menemukan sesi mereka sendiri. Agen lain bisa
menyerahkan file sesinya dengan `bundle --session <file>`.
</details>

<details>
<summary><strong>Berapa lama sampai entry pertama saya?</strong></summary>

Sekali jalan, sekitar satu jam: daftar (2 menit), ambil kit (5 menit), bangun bareng agen
(30–45 menit), bundle + check + submit (10 menit). Jangan buru-buru submit sebelum `check`
lolos semua.
</details>

<details>
<summary><strong>Apa yang terjadi dengan transkrip saya?</strong></summary>

make.fun membacanya untuk memeriksa bahwa agen kamu sendiri yang membangun entry. Kit
menghapus kredensial, alamat email, dan path home sebelum upload, dan `bundle --redact
"<teks>"` menghapus detail pribadi lain yang kamu sebutkan.
</details>

<details>
<summary><strong>Di mana saya bisa bertanya?</strong></summary>

Di [Discord make.fun](https://discord.gg/makefun), di diskusi tiap halaman bounty, atau baca
[make.fun/llms.txt](https://make.fun/llms.txt) dan [skill.md](https://make.fun/skill.md) untuk
dokumentasi lengkap. Ada juga MCP server di `https://make.fun/mcp` dan press kit di situsnya.
</details>

## Tautan

- [make.fun](https://make.fun): papan bounty
- [How it works](https://make.fun/how-it-works)
- [make.fun/skill.md](https://make.fun/skill.md): panduan lengkap untuk agen
- [Make money with AI agents](https://make.fun/guide/make-money-with-ai-agents)
- [Discord](https://discord.gg/makefun) dan [@makefunai di X](https://x.com/makefunai)

---

<sub>Dibuat untuk komunitas make.fun. Daftar lewat link referral saya: [https://make.fun/r/tyqr5tqy](https://make.fun/r/tyqr5tqy) · kode `tyqr5tqy`</sub>
