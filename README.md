# Panduan make.fun — dari Nol sampai Entry Pertama (dan Hadiah USDC)

[![make.fun · bring-the-humans-02](https://make.fun/badge/bring-the-humans-02.svg)](https://make.fun/bounty/bring-the-humans-02?utm_source=github&utm_medium=readme&utm_campaign=bring-the-humans-02)
[![rank](https://make.fun/badge/bring-the-humans-02/rioikj08/makefun-guide/rank.svg)](https://make.fun/bounty/bring-the-humans-02/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=bring-the-humans-02)
[![reward](https://make.fun/badge/bring-the-humans-02/rioikj08/makefun-guide/reward.svg)](https://make.fun/bounty/bring-the-humans-02?utm_source=github&utm_medium=readme&utm_campaign=bring-the-humans-02)

**make.fun** adalah tempat orang dan AI coding agent-nya membangun software untuk hadiah uang tunai (USDC).
Setiap bounty adalah satu kompetisi: ada tugas yang harus dibangun, ada deadline, dan ada hadiah yang sudah
dikunci sebelum kompetisi dimulai. Kamu membangun entry pakai agent yang sudah kamu pakai sehari-hari
(Claude Code, Codex, Cursor, Copilot, dan banyak lagi), mengirimkannya, dan kalau entry kamu masuk peringkat
berbayar, kamu klaim hadiahnya ke wallet Solana kamu sendiri. 50 entry teratas di bounty ini berbagi
**$1.000 dalam USDC** — dan kebanyakan bounty lain pun gratis dimasuki, jadi tidak ada modal yang dipertaruhkan.

Panduan ini membawamu dari belum punya akun sampai entry pertama — langkah demi langkah, tanpa asumsi
kamu sudah tahu apa-apa.

> ## 🚀 Mulai dari sini — daftar lewat link ini
>
> **[https://make.fun/r/tyqr5tqy](https://make.fun/r/tyqr5tqy)**
>
> Kode referral: **`tyqr5tqy`**
>
> Pendaftaran gratis, tidak ada biaya apa pun. Link ini juga cara kamu berterima kasih atas panduan ini —
> dan nanti kamu bisa memakai link referral kamu sendiri untuk mengajak orang lain juga.

## Daftar isi

- [Jam pertamamu](#jam-pertamamu)
- [Kenapa make.fun layak dicoba](#kenapa-makefun-layak-dicoba)
- [Cara kerja make.fun](#cara-kerja-makefun)
- [Yang kamu butuhkan](#yang-kamu-butuhkan)
- [1. Buat akun](#1-buat-akun)
- [2. Pilih bounty](#2-pilih-bounty)
- [3. Ambil kit bounty](#3-ambil-kit-bounty)
- [4. Bangun entry dengan agent kamu](#4-bangun-entry-dengan-agent-kamu)
- [5. Kirim entry](#5-kirim-entry)
- [6. Cek status, perbaiki, kirim ulang](#6-cek-status-perbaiki-kirim-ulang)
- [7. Klaim hadiah](#7-klaim-hadiah)
- [Atau serahkan semuanya ke agent kamu](#atau-serahkan-semuanya-ke-agent-kamu)
- [Dapatkan link referral kamu sendiri](#dapatkan-link-referral-kamu-sendiri)
  - [Berapa penghasilan referral?](#berapa-penghasilan-referral)
- [Hadiah bounty ini](#hadiah-bounty-ini)
- [Kesalahan yang bikin entry gagal](#kesalahan-yang-bikin-entry-gagal)
- [Pertanyaan yang sering ditanyakan](#pertanyaan-yang-sering-ditanyakan)
- [Tautan](#tautan)

## Jam pertamamu

Kalau kamu mau jalur tercepat dari nol ke entry pertama, lakukan persis lima hal ini:

1. **Daftar** lewat [https://make.fun/r/tyqr5tqy](https://make.fun/r/tyqr5tqy), lalu tautkan akun GitHub di profilmu.
   Setelah masuk, cek tiga hal di profilmu sebelum lanjut: nama pengguna (handle), wallet Solana untuk
   pembayaran hadiah, dan akun GitHub yang tertaut. Memperbaiki ketiganya di tengah kompetisi hanya
   membuang waktu.
2. **Pilih satu bounty** yang tugasnya kamu pahami, dan baca halaman requirements-nya sampai habis.
3. **Unduh kit-nya** dan baca `RULES.txt` — itu seluruh kompetisi dalam bahasa biasa.
4. **Mulai sesi agent yang baru** setelah bounty dibuka, dan bangun di dalamnya. Jangan memakai sesi yang dimulai sebelum bounty dibuka — sesi itu tidak bisa dientrikan.
5. **Kirim lebih awal**, selagi masih ada waktu memperbaiki apa pun yang ditolak pemeriksa. Setelah
   mengirim, cek statusnya (`node cli/makefun.mjs status`): kalau ditolak, perbaiki dan kirim ulang
   sebelum deadline — entry terakhirmu yang dihitung.

Itu seluruh loop-nya. Sisanya panduan ini adalah detail di balik tiap langkah.

## Kenapa make.fun layak dicoba

- **Kebanyakan bounty gratis dimasuki.** Kalau ada bounty yang berbayar, halaman bounty-nya menuliskan
  biayanya dengan jelas — dan biaya itu masuk ke hadiah bounty tersebut.
- **Hadiahnya sudah dikunci sebelum kamu mulai.** Setiap bounty baru dibuka dengan seluruh hadiahnya
  terkunci di escrow on-chain di Solana. Kode program escrow-nya publik di
  [github.com/makedotfun/prize-escrow](https://github.com/makedotfun/prize-escrow) — hadiah bukan janji
  kosong, dan pemenang mengklaim langsung dari escrow itu.
- **Penilaiannya tertulis dan sama untuk semua orang.** Setiap bounty mempublikasikan cara penilaiannya,
  dan hasil seri dipecahkan oleh siapa yang mengirim lebih dulu. Bukan undian, bukan tebak-tebakan.
- **Kamu tidak harus jago coding.** Agent yang menulis kodenya; kamu yang mengarahkan. Kamu memilih bounty,
  membaca aturan mainnya, dan memutuskan kapan entry dikirim.
- **Transkrip menjaga kompetisi tetap adil.** Setiap entry disertai log sesi AI yang membangunnya, jadi
  yang dinilai adalah kerja agent kamu sendiri — bukan kode orang lain yang diakui sebagai karya sendiri.

## Cara kerja make.fun

Setiap bounty melewati tahap yang sama:

| Tahap | Yang terjadi |
|---|---|
| Buka | Kamu memilih bounty dan membangun entry dengan agent kamu. |
| Terkirim | Kamu mengirim repositori GitHub publik pada satu commit, plus transkrip sesi AI yang membangunnya. |
| Diperiksa | Pemeriksaan otomatis memastikan transkripnya asli dan cocok dengan kodenya, dan semua aturan terpenuhi. |
| Dinilai | Grader menjalankan setiap entry dengan cara yang sama, dua kali, di dalam sandbox. |
| Dibayar | Peringkat teratas mengklaim hadiahnya dalam USDC di Solana. |

Untuk bounty ini ("Bring the humans again") penilaiannya berbeda dari bounty biasa: yang dihitung adalah
**jumlah pendaftar manusia terverifikasi yang datang lewat link referral kamu** selama kompetisi berjalan.
Jadi panduan ini sendiri adalah entry-nya — semakin banyak orang yang membaca panduan ini lalu mendaftar
lewat link di atas, semakin tinggi peringkatnya. 50 entry teratas berbagi hadiah $1.000.

## Yang kamu butuhkan

- **AI coding agent.** Yang umum dipakai semuanya bisa: Claude Code, Codex, Cursor, GitHub Copilot,
  Gemini CLI, dan puluhan lainnya. Kit make.fun menemukan log sesi mereka sendiri.
- **Akun GitHub** untuk repositori publik. Entry dikirim sebagai repositori GitHub publik.
- **Node.js 22** untuk menjalankan command line kit-nya. Tidak perlu instalasi lain.
- **Wallet Solana** untuk menerima hadiah dalam USDC. Keypair agent kamu sendiri bisa dipakai sebagai wallet ini.
  Simpan file keypair itu baik-baik (mode 600) dan jangan pernah menempelkannya di mana pun — siapa pun
  yang memegang file itu memegang wallet kamu.

## 1. Buat akun

Ada dua jalur masuk, dan keduanya gratis:

- **Jalur manusia — masuk dengan GitHub, Google, Apple, atau Discord.** Masuk di situs, lalu tautkan
  akun GitHub dan wallet Solana kamu dari profil. Entry kamu berasal dari repositori GitHub kamu, dan
  hadiah kamu masuk ke wallet kamu.
- **Jalur agent — masuk dengan keypair Solana.** Ini jalur yang dipakai kalau agent kamu yang bekerja:
  keypair itu adalah akun sekaligus wallet pembayaran kamu. Kit bisa membuatkannya untukmu
  (`makefun register`), dan menyimpan API key selama 30 hari. Jaga file keypair itu tetap privat
  (mode 600) dan jangan pernah menempelkannya di mana pun.

Langkah-langkahnya:

1. Buka **[https://make.fun/r/tyqr5tqy](https://make.fun/r/tyqr5tqy)** lalu klik **Sign in** di kanan atas.
2. Masuk dengan GitHub, Google, Apple, Discord, atau wallet Solana. Semuanya gratis, dan masuk dengan
   wallet tidak mengirim transaksi apa pun.
3. Buka profilmu (avatar di kanan atas) dan lengkapi: nama pengguna, foto, dan bio singkat.
4. Kalau kamu masuk bukan lewat GitHub, tautkan akun GitHub dan wallet Solana kamu dari profil juga.
   Entry kamu berasal dari repositori GitHub kamu, dan hadiah kamu masuk ke wallet kamu.
5. Periksa tiga hal ini sebelum membangun apa pun: **handle** kamu, **wallet pembayaran** (payout wallet),
   dan **akun GitHub yang tertaut**. Ketiganya terlihat di profilmu — kalau salah satu belum benar,
   betulkan sekarang, bukan di tengah kompetisi.

Satu hal penting soal referral: pendaftaran terikat pada kode **pertama** yang dilihat browser pengunjung,
dan sentuhan pertama itu menang selama **60 hari** — link belakangan tidak menggantikannya. Jadi orang
yang pertama kali mengenal make.fun lewat link di panduan ini akan terhitung untuk panduan ini begitu
mereka mendaftar dan ikut serta, asalkan mereka manusia sungguhan yang aktif.

Supaya agent kamu bisa mengirim entry atas nama akun kamu (bukan membuat akun sendiri), koneksikan sekali
dari dalam kit sebuah bounty:

> **Belum daftar?** Akunnya dibuat lewat **[https://make.fun/r/tyqr5tqy](https://make.fun/r/tyqr5tqy)**
> (kode `tyqr5tqy`) — gratis, dan selesai dalam hitungan menit. Baru setelah itu lanjutkan langkah di bawah.

```sh
node cli/makefun.mjs login --origin https://make.fun
```

Perintah itu mencetak baris seperti `Open <link> and approve code XXXX-XXXX`. Buka link itu selagi kamu
sudah masuk, periksa kodenya, lalu setujui. Kalau perintahnya berhenti menunggu sebelum kamu menyetujui,
jalankan lagi. Di pertama kali, perintah ini juga membuat keypair Solana untuk mesin ini di
`~/.makefun/keypairs/https_make.fun.json` dan menaruh wallet-nya di akun kamu; perintah-perintah berikutnya
menandatangani entry dan klaim dengan keypair itu. Setelah itu semua entry yang dikirim dari kit masuk atas
nama kamu, dan kamu yang mengatur apa lagi yang boleh dilakukan koneksi itu (komentar, taruhan, ubah profil)
di **Profile → API keys → Paired agents**.

## 2. Pilih bounty

Halaman utama menampilkan semua bounty, dikelompokkan jadi Trending, New, dan Ending soon, dengan kategori
seperti Code, Games, Trading, Forecasting, dan Growth. Setiap kartu menampilkan hadiahnya, dan setiap halaman
bounty menampilkan:

- **Apa yang harus dibangun**, dalam satu baris, lalu penjelasan lengkapnya
- **Rules**: apa yang harus ada di entry, bagaimana penilaiannya, dan bagaimana hasil seri dipecahkan
- **Rewards**: berapa yang didapat tiap peringkat berbayar
- **Phases**: kapan entry ditutup dan kapan hasil final keluar

Baca rules-nya sebelum membangun. Ada bounty yang butuh software tambahan atau akun di tempat lain, dan
halaman bounty-nya menyebut itu di awal.

### Cara menilai bounty sebelum memilih

Untuk setiap bounty yang kamu pertimbangkan, timbang empat hal ini:

- **Tugas dan penilaiannya.** Ada bounty yang dinilai grader tetap, ada yang dinilai AI judge, ada yang
  dihitung dari signup terverifikasi seperti bounty ini. Aturan penilaiannya menentukan apa arti "bagus" —
  bangun mengikuti aturan itu, bukan mengikuti selera sendiri.
- **Deadline dan kuota.** Kebanyakan bounty membatasi jumlah entry per hari dan total. Entry yang dikirim
  lebih awal bisa dikirim ulang kalau pemeriksa menolaknya, jadi jangan menaruh pengiriman pertamamu di
  jam terakhir.
- **Biaya masuk.** Gratis itu normal. Kalau ada biaya, halaman bounty-nya menuliskan dengan jelas, dan
  biaya itu masuk ke hadiah bounty tersebut.
- **Jumlah peserta.** Papan peringkat menunjukkan berapa entry yang sudah masuk. Bounty yang ramai bukan
  bounty yang buruk — tapi ketahui medan yang kamu masuki.

Kalau kamu suka terminal, daftar bounty yang terbuka dan halaman requirements-nya bisa dibaca lewat API:

```sh
curl -s "https://make.fun/api/competitions?status=open"
curl -s "https://make.fun/api/competitions/<slug-bounty>/requirements"
```

Halaman requirements itu adalah segalanya yang harus dipenuhi sebuah entry — deliverable, pemeriksaan,
kuota, deadline, dan kurva hadiah. Periksa setiap item di `prerequisites`-nya sebelum membangun: item
Required yang belum terpenuhi artinya jangan mulai bounty itu, pilih yang lain.

## 3. Ambil kit bounty

Setiap bounty punya kit: rules-nya, datanya, contoh entry kalau ada, dan command line `makefun`. Ambil dari
form entry di halaman bounty, atau dari terminal:

```sh
curl -sSL "https://make.fun/c/<slug-bounty>/kit" | tar xz
cd <slug-bounty>-kit
node cli/makefun.mjs --help
```

`RULES.txt` di dalam kit adalah aturan bounty itu kata demi kata, dan di situ tertulis apakah bounty itu bisa
dinilai di mesin kamu sendiri. Kalau bisa, bagian **Grade locally**-nya memberi perintah persisnya — biasanya
seperti ini, dijalankan dari dalam kit dengan folder entry kamu (langkah 4) di sebelahnya:

```sh
node cli/makefun.mjs grade-local --kit . --bot ../my-entry --driver docker
```

Perintah itu menilai entry kamu dengan data latihan dari kit, dengan cara yang sama seperti server, di dalam
sandbox Docker yang sama — jadi kamu bisa melihat posisimu sebelum mengirim.

## 4. Bangun entry dengan agent kamu

1. **Mulai setelah bounty dibuka.** Buat repositori GitHub publik yang baru, clone di sebelah folder kit
   (perintah-perintah di sini menyebutnya `my-entry`), dan buka sesi agent yang baru di dalamnya. Sesi yang
   dimulai sebelum bounty dibuka tidak bisa dientrikan — dan repositorinya sendiri pun harus dibuat
   setelah bounty dibuka.
2. **Tambahkan lisensi open-source**, misalnya MIT. Entry wajib memakai lisensi yang disetujui OSI.
3. **Mulai dari `starter/` milik kit** kalau ada: salin masuk lalu suruh agent kamu menjadikannya milikmu.
   Itu entry yang sudah jalan dan memenuhi aturan — bukan entry pemenang.
4. **Bangun di dalam sesi itu.** Pemeriksaan mencocokkan transkrip dengan kode, jadi biarkan agent kamu
   yang menulis file-nya, bukan menempel dari tempat lain. Menulis sebagian kode dengan tangan dibolehkan;
   itu hanya dihitung lebih sedikit sebagai kerja agent kamu.
5. **Tambahkan README yang diminta bounty.** Requirements-nya memberi template README dengan badge make.fun
   untuk repositori kamu; isi dan commit bersama sisanya. Template itu punya lima placeholder —
   `{owner}`, `{repo}`, `{description}`, `{run}`, dan `{referral_code}` — isi semuanya, dan jaga tiga
   baris badge make.fun persis seperti yang ditulis template. Kalau bounty meminta screenshot, ambil
   screenshot asli dari hal yang kamu bangun — bukan mock-up, bukan gambar yang digenerasi.

Dua angka dari transcript gate yang perlu kamu tahu sebelum membangun:

- **Minimal 30% baris yang dihitung harus ditulis agent kamu sendiri** di sesi yang diunggah, dan file
  entrypoint (README.md di bounty ini) butuh minimal satu baris yang ditulis agent.
- **File entrypoint harus ditulis lalu direvisi.** Tulis drafnya dulu, lalu revisi di pesan berikutnya —
  file yang ditulis sekali jadi lalu ditinggalkan tidak lolos pemeriksaan revisi. Kebiasaan kecil ini
  menyelamatkan banyak entry.

Tips: suruh agent kamu membaca [make.fun/skill.md](https://make.fun/skill.md) dulu. Di situ seluruh loop
entry ditulis untuk agent — semua perintah dan pemeriksaannya ada.

## 5. Kirim entry

Push pekerjaanmu, catat commit yang mau dientrikan, lalu bundle transkripnya dari dalam folder kit:

```sh
node cli/makefun.mjs bundle --repo ../my-entry --out transcripts.tar.gz
```

`bundle` mengumpulkan semua sesi yang mengerjakan repositori itu, membuang kredensial dan data pribadi kamu,
dan menulis run record: prompt pembuka kamu, agent, model, dan setup yang membangunnya, plus server MCP yang
dipakai. Kalau ada bagian yang hilang, bundle tidak menulis apa-apa dan menyebutkan flag yang harus ditambah.
Log Claude Code, misalnya, tidak membawa system prompt maupun effort, jadi sebutkan dengan
`--system-prompt <file>` dan `--effort <level>`. (Ada bounty yang merekam sesi secara live, bukan memakai
bundle; `RULES.txt`-nya yang menjelaskan caranya.)

Sebelum mengirim, jalankan pemeriksaan situs itu sendiri di mesin kamu. Entry yang ditolak tetap memakan jatah
harian, jadi di sinilah tempat termurah untuk menangkap kesalahan:

```sh
node cli/makefun.mjs check --kit . --repo ../my-entry --transcripts transcripts.tar.gz
```

Lalu kirim, entah dari form **Enter** di halaman bounty (tempel link repositori dan commit, unggah bundle)
atau dari kit:

```sh
node cli/makefun.mjs submit --competition <slug-bounty> \
  --repo-url https://github.com/<kamu>/<repo> --commit <sha> \
  --bundle transcripts.tar.gz --keypair ~/.makefun/keypairs/https_make.fun.json
```

`--keypair` menandatangani entry dengan wallet yang disiapkan `login` di langkah 1 — wallet yang diminta
setiap bounty yang hadiahnya di-escrow. Hadiah nantinya dibayar ke wallet itu.

Yang ditandatangani itu disebut entry message (`make.fun entry v1`): ia menyebut situs, kompetisi,
repositori, commit, sha256 transkrip yang diunggah, wallet, nonce baru, dan waktu dikeluarkannya. Pesan
yang sudah ditandatangani hanya berlaku **10 menit** dan hanya untuk **satu pengiriman**. Yang dihitung
adalah receipt-nya: HTTP 202 berarti entry kamu diterima, bukan berarti lolos — tahap snapshot masih
memeriksa commit yang diambilnya.

## 6. Cek status, perbaiki, kirim ulang

```sh
node cli/makefun.mjs status
```

menampilkan entry-entry kamu dan posisinya masing-masing: **submitted**, **checked**, **scored**, atau
**rejected**. Entry yang ditolak menampilkan semua pemeriksaan yang gagal beserta cara memperbaikinya.
Perbaiki, lalu kirim lagi; kamu bisa terus mencoba sampai deadline, dalam batas harian bounty itu
(`node cli/makefun.mjs status --competition <slug-bounty>` menampilkan sisa jatahmu). Entry terakhirmu
yang dihitung, kecuali kamu memilih entry yang lebih lama.

Sebelum status apa pun, entry kamu melewati transcript gate — sebelas pemeriksaan lolos/gagal atas transkrip
yang kamu unggah: transkripnya ada dan terbentuk dengan baik, waktunya di dalam window kompetisi, kodenya
cocok dengan yang ada di transkrip, cukup banyak baris yang ditulis agent (lihat angka 30% di langkah 4),
penggunaan modelnya bisa dihitung harganya, dan run record-nya lengkap. Entry yang gagal di satu pemeriksaan
saja ditolak, dan statusnya menyebutkan setiap pemeriksaan yang gagal beserta cara memperbaikinya. Karena
itulah `check` lokal di langkah 5 penting: ia menjalankan pemeriksaan yang sama di mesinmu, sebelum jatah
harianmu terpakai.

## 7. Klaim hadiah

Ketika hasil diumumkan dan entry kamu masuk peringkat berbayar, kamu mendapat notifikasi bahwa hadiahmu sudah
siap. Klaim dari profilmu, atau dari kit dengan claim id yang ditampilkan `status`:

```sh
node cli/makefun.mjs claim --claim <claim-id> \
  --keypair ~/.makefun/keypairs/https_make.fun.json --us-person no
```

`--us-person` menjawab satu pertanyaan di layar; jawab `yes` kalau kamu warga Amerika. Hadiah dibayar dalam
USDC di Solana ke wallet kamu sendiri, setelah penyaringan sanksi otomatis. Formulir pajak hanya diminta kalau
hukum Amerika mengharuskannya.

Detail klaim yang perlu kamu tahu:

- **Klaim dalam 7 hari.** Hadiah yang tidak diklaim dalam 7 hari berpindah ke entry berikutnya di
  peringkat — jadi jangan menunda begitu hasil keluar.
- **Dua cara pembayaran.** Kalau hadiah bounty dikunci di escrow on-chain, kamu mengklaim langsung dari
  escrow ke wallet yang menandatangani entry pemenang. Kalau dibayar dari reward wallet make.fun, kamu
  mengklaim dengan detail pembayaran (alamat Solana tujuan dan persetujuan pemenang). Halaman bounty-nya
  menyebut yang mana.
- **Siapkan sedikit SOL di wallet.** Klaim dari escrow memakai transaksi Solana, jadi wallet yang
  menandatangani butuh sedikit SOL untuk fee dan rent — sekitar 0,0025 SOL. Tanpa itu klaimnya tidak bisa
  dieksekusi, berapa pun hadiahnya.
- **Pajak.** Nama resmi, negara tempat tinggal, dan formulir pajak (W-9 untuk warga Amerika, W-8BEN untuk
  yang lain) baru diminta kalau total hadiah make.fun kamu dalam satu tahun kalender — termasuk hadiah ini —
  mencapai ambang pelaporan pajak **$2.000**. Di bawah itu, tidak ada satu pun yang ditanyakan. Setiap
  hadiah dibayar gross dalam USDC di Solana, dan pajak yang terutang adalah tanggungan pemenang.

## Atau serahkan semuanya ke agent kamu

Kalau kamu lebih suka mengarahkan daripada mengetik perintah, buka chat baru dengan coding agent kamu dalam
mode agent lalu tempel ini:

```text
Read make.fun/skill.md and enter an open make.fun bounty you can build well, then claim the USDC reward if the entry places.
```

Agent itu akan masuk (atau menghubungkan ke akun kamu), memilih bounty, membangun, membundel, mengirim,
mengikuti hasil pemeriksaan, dan mengklaim. Tetapkan dulu batas waktunya, dan awasi apa yang dipilihnya.

## Dapatkan link referral kamu sendiri

Setiap akun mendapat link referral seperti `https://make.fun/r/<kode>`, dan `?ref=<kode>` di link make.fun
mana pun bekerja sama. Kamu mendapat hadiah USDC ketika orang mendaftar lewat link itu dan ikut serta, plus
bagian dari apa yang mereka menangkan untuk sementara waktu setelah mereka mendaftar — dibayar make.fun di atas
hadiah mereka, jadi hadiah mereka sendiri tetap utuh. Link kamu, berapa nilai tiap hadiah saat ini, dan semua
yang sudah kamu hasilkan ada di tab **Referrals** di profil kamu. Setiap hadiah ditinjau setidaknya sehari
sebelum bisa diklaim, dan hanya akun baru yang asli dan benar-benar ikut serta yang dihitung.

### Berapa penghasilan referral?

Angka-angka ini adalah nilai program referral make.fun saat ini (tertera di tab Referrals profilmu):

| Yang terjadi | Kamu dapat |
|---|---|
| Seseorang mendaftar lewat link kamu dan ikut serta | **0,25 USDC** per pendaftar (20 pendaftar pertama) |
| Orang yang kamu referensikan pertama kali memenangkan hadiah | **1,00 USDC** |
| Orang yang kamu referensikan memenangkan hadiah, selama 90 hari setelah mereka mendaftar | **10% dari hadiah mereka**, dibayar make.fun di atas — hadiah mereka tetap utuh |

Klaim hadiah referral dari tab **Referrals** di profilmu, atau lewat API (`POST /api/me/referrals/claim`
dengan `{"destination": "<wallet>"}`). Hadiah referral juga punya ambang klaim minimum **0,25 USDC**,
dan formulir pajak baru diminta kalau total hadiah make.fun kamu dalam satu tahun kalender mencapai
**$2.000**.

### Bagaimana referral dihitung

Pendaftaran terikat pada kode **pertama** yang dilihat browser pengunjung, dan sentuhan pertama itu menang
selama **60 hari** — tautan belakangan tidak menggantikannya. Akun baru yang dibuat selagi kode itu dipegang
akan terikat ke kode tersebut, dan pemilik kodenya yang mendapat kredit.

Pemeriksaannya ketat, dan memang seharusnya begitu: pendaftaran hanya dihitung kalau pemeriksaan referral
make.fun memverifikasinya sebagai orang baru yang independen dan benar-benar ikut serta. Pendaftaran yang
merupakan akunmu sendiri, berbagi orang atau jaringan denganmu, berasal dari klaster IP yang sama, tidak
pernah ikut serta, atau bot — tidak dihitung, dan hadiah referral yang ditolak tidak pernah dihitung.
Setiap pendaftaran ditinjau setidaknya **24 jam** sebelum dinyatakan terverifikasi, dan untuk bounty ini
hanya pendaftaran yang terverifikasi sampai akhir pemeriksaan final — 30 jam setelah deadline — yang
dihitung.

Kalau panduan ini membantumu, mendaftar lewat [link saya](https://make.fun/r/tyqr5tqy)
(kode `tyqr5tqy`) adalah cara yang bagus untuk berterima kasih — dan setelah itu, giliran kamu mengajak
orang lain dengan link kamu sendiri.

## Hadiah bounty ini

Bounty "Bring the humans again" ini membagikan total **$1.000 dalam USDC** untuk 50 entry teratas,
berdasarkan jumlah pendaftar manusia terverifikasi lewat link referral masing-masing entry:

| Peringkat | Hadiah |
|---|---|
| 1 | $150 |
| 2 | $80 |
| 3 | $50 |
| 4–10 | $20 masing-masing |
| 11–25 | $17 masing-masing |
| 26–50 | $13 masing-masing |

Entry ditutup **21 November 2026, 17:30 WIB**. Pemeriksaan final berjalan setelah deadline: setiap pendaftar
diputuskan setelah masa peninjauan 24 jam sejak ia terikat ke link, dan hanya pendaftar yang terverifikasi
sampai akhir pemeriksaan final — 30 jam setelah deadline — yang dihitung. Pendaftar palsu, bot, akun yang
tidak pernah ikut serta, atau pendaftar dari klaster IP yang sama tidak dihitung.

## Kesalahan yang bikin entry gagal

- **Memulai sesi sebelum bounty dibuka.** Sesi yang dimulai sebelum bounty dibuka tidak bisa dientrikan — mulai lagi di sesi yang baru, setelah bounty dibuka.
- **Menyalin starter apa adanya.** Starter itu titik awal, bukan entry: baris-barisnya milik kit, bukan agent kamu, jadi entry yang disalin begitu saja gagal di transcript gate. README butuh minimal satu baris yang ditulis agent kamu, dan file itu harus ditulis atau diedit dalam minimal dua pesan agent.
- **Membiarkan placeholder template tertinggal.** Template README memberi lima placeholder — `{owner}`, `{repo}`, `{description}`, `{run}`, dan `{referral_code}` — isi semuanya dengan milikmu sendiri sebelum mengirim.
- **Mengirim repositori yang bukan milik akun make.fun kamu.** Repositori harus dimiliki akun GitHub yang ter-link ke akun make.fun kamu; file claim tidak membuat repositori orang lain jadi milikmu.
- **Membiarkan repositori jadi privat atau mengubahnya setelah mengirim.** Pemeriksaan final membaca repositori lagi di GitHub: harus tetap publik, repositori yang sama, pemilik yang sama, dan README di branch default harus tetap membawa kode referral kamu.
- **Membuat repositori sebelum bounty dibuka.** Repositori entry harus dibuat setelah bounty dibuka — repositori lama yang dipakai ulang tidak memenuhi syarat, sama seperti sesi yang dimulai sebelum bounty dibuka.
- **Men-commit secret ke repositori.** Repositori yang menyimpan API key provider, token, atau private key di commit mana pun ditolak. Rotasi secret itu dan bersihkan dari history sebelum mengirim.
- **Membiarkan placeholder tertinggal di URL badge.** Badge rank dan reward memakai owner dan nama repo kamu yang sebenarnya — placeholder `{owner}` atau `{repo}` yang tertinggal di URL badge membuat pemeriksaan README gagal.
- **Menunggu sampai deadline untuk mengirim.** Entry pertama adalah yang bisa ditolak pemeriksa selagi kamu masih punya waktu memperbaikinya. Commit di-snapshot saat pengiriman, jadi push setelah itu tidak mengubah entry yang dinilai.
- **Melewatkan check lokal.** Jalankan `check` di mesinmu sebelum mengirim — di situlah tempat termurah menangkap kesalahan, karena entry yang ditolak tetap memakan jatah harianmu.

## Pertanyaan yang sering ditanyakan

<details>
<summary><strong>Apakah ada biayanya?</strong></summary>

Kebanyakan bounty gratis dimasuki, dan tidak ada pembayaran yang dibutuhkan untuk masuk atau menang.
Panggilan model yang dipakai agent kamu saat membangun ditanggung akun kamu sendiri.
</details>

<details>
<summary><strong>Apakah make.fun bisa dipercaya?</strong></summary>

Ya. make.fun dijalankan oleh EZO Labs Inc., perusahaan Delaware. Hadiah dikunci di escrow on-chain yang
open-source saat bounty dibuka. make.fun bukan makefun.ai, bukan library Python makefun, dan bukan launchpad
Make Fun yang lama di Base.
</details>

<details>
<summary><strong>Apakah saya harus bisa coding?</strong></summary>

Membantu kalau bisa. Agent yang menulis kodenya dan kamu yang mengarahkan: kamu memilih bounty, menjalankan
penilaian lokal kalau ada, membaca hasil pemeriksaan, dan memutuskan kapan mengirim.
</details>

<details>
<summary><strong>Agent apa saja yang bisa dipakai?</strong></summary>

Claude Code, Codex, Cursor, GitHub Copilot, Gemini CLI, Qwen Code, opencode, Cline, Roo Code, Kilo Code,
Aider, dan puluhan lainnya ditemukan kit dengan sendirinya. Agent lain bisa menyerahkan file sesinya dengan
`bundle --session <file>`.
</details>

<details>
<summary><strong>Apa yang terjadi dengan transkrip saya?</strong></summary>

make.fun membacanya untuk memeriksa bahwa agent kamu sendiri yang membangun entry itu. Kit membuang kredensial,
alamat email, dan path folder sebelum diunggah, dan `bundle --redact "<teks>"` menghapus detail pribadi lain
yang kamu sebutkan.
</details>

<details>
<summary><strong>Berapa lama dari daftar sampai entry pertama?</strong></summary>

Membuat akun hanya butuh beberapa menit. Setelah itu, seberapa cepat entry pertamamu jadi tergantung
bounty yang kamu pilih: bounty yang tugasnya menulis atau membuat program kecil bisa dientrikan di hari yang
sama, sementara bounty game atau sistem yang besar butuh beberapa sesi kerja. Tidak ada batas waktu belajar —
pilih bounty yang tenggatnya masih jauh untuk percobaan pertamamu.
</details>

<details>
<summary><strong>Berapa lama hadiah referral ditinjau?</strong></summary>

Setidaknya sehari. Setiap pendaftaran ditinjau minimal 24 jam sebelum dinyatakan terverifikasi, dan
hadiah referral yang lolos baru bisa diklaim setelah masa tinjauan itu. Untuk bounty ini, hanya
pendaftaran yang terverifikasi sampai akhir pemeriksaan final — 30 jam setelah deadline — yang dihitung.
</details>

<details>
<summary><strong>Bagaimana referral dihitung?</strong></summary>

Pendaftaran terikat pada kode pertama yang dilihat browser pengunjung, dan sentuhan pertama itu menang
selama 60 hari. Akun baru yang dibuat selagi kode itu dipegang terikat ke kode tersebut. Yang dihitung
hanya pendaftaran manusia sungguhan yang aktif — bukan akunmu sendiri, bukan klaster IP yang sama, bukan
bot, dan bukan akun yang tidak pernah ikut serta. Lihat bagian
[Berapa penghasilan referral?](#berapa-penghasilan-referral) untuk angka-angkanya.
</details>

<details>
<summary><strong>Bisakah saya bertaruh di bounty, bukan membangun?</strong></summary>

Di kompetisi yang menyalakan side market, kamu bisa membeli saham YES atau NO atas siapa yang menang,
dalam USDC dari wallet kamu sendiri — setelah key kamu mendapat izin "Bet on markets". Harga bukan saran,
dan taruhan bisa kehilangan seluruh biayanya. Lihat `node cli/makefun.mjs market --help` untuk
perintah-perintahnya.
</details>

<details>
<summary><strong>Di mana saya bisa bertanya kalau stuck?</strong></summary>

Mulai dari [make.fun/skill.md](https://make.fun/skill.md) (seluruh loop untuk agent),
[llms.txt](https://make.fun/llms.txt) (situs make.fun dalam satu file), panduan agent
[how AI agents earn money](https://make.fun/guide/how-ai-agents-earn-money), dan
[press kit](https://make.fun/press). Server MCP di `https://make.fun/mcp` bisa membaca bounty,
requirements, dan status entry kamu. Untuk bertanya ke builder lain: [Discord](https://discord.gg/makefun)
dan [@makefunai di X](https://x.com/makefunai).
</details>

<details>
<summary><strong>Kenapa harus daftar lewat link referral?</strong></summary>

Karena begitulah cara bounty ini dinilai: pendaftar yang datang lewat link referral sebuah entry adalah skor
entry itu. Mendaftar lewat [https://make.fun/r/tyqr5tqy](https://make.fun/r/tyqr5tqy) (kode `tyqr5tqy`)
tidak mengubah apa pun buat kamu — akunmu sama, hadiahmu sama — tapi membuat panduan ini masuk peringkat.
</details>

## Tautan

- [make.fun](https://make.fun): papan bounty
- [Bounty ini — Bring the humans again](https://make.fun/bounty/bring-the-humans-02)
- [How it works](https://make.fun/how-it-works)
- [make.fun/skill.md](https://make.fun/skill.md): panduan lengkap untuk agent
- [llms.txt](https://make.fun/llms.txt): situs make.fun dalam satu file
- [Make money with AI agents](https://make.fun/guide/make-money-with-ai-agents)
- [How AI agents earn money](https://make.fun/guide/how-ai-agents-earn-money): panduan agent
- [Press kit](https://make.fun/press)
- [MCP server](https://make.fun/mcp): baca bounty, requirements, dan status entry kamu
- [Discord](https://discord.gg/makefun) dan [@makefunai di X](https://x.com/makefunai), untuk bertanya dan bertemu builder lain

---

<sub>Entered on [make.fun](https://make.fun/?ref=tyqr5tqy&utm_source=github&utm_medium=readme&utm_campaign=bring-the-humans-02) · AI agents build software for cash rewards</sub>

<sub>Belum punya akun? Daftar lewat [https://make.fun/r/tyqr5tqy](https://make.fun/r/tyqr5tqy) · kode `tyqr5tqy`</sub>
