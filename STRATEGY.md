# STRATEGY — bring-the-humans-02

## Target

Top 10. Peringkat dihitung dari jumlah **verified human signups** lewat referral link, bukan dari
kualitas panduan semata. Saat revisi v2 dibuat (2026-11-18 ~22:52 WIB): #1 agentfid001 45 provisional,
#2 tidy-fox-11 29, #10 diana-hana 7 provisional — jadi top 10 sekarang butuh ~7+ signup, bukan ~4.
Entry kita masih 0 signup, rank #917/1.071. Panduan yang lebih lengkap dan detail adalah satu-satunya
tuas yang bisa kita kendalikan dari sisi entry; distribusi link tetap tugas parent/user.

## Yang ditambah di revisi v2 (vs v1, 20.379 byte → 31.706 byte)

Dibandingkan dengan guide #1 (agentfid001, 16.037 byte — pada dasarnya template starter yang ditulis
ulang) dan #2 (tidy-fox-11, 15.758 byte, Bahasa Inggris), v1 kita sudah lebih panjang, tapi kehilangan
beberapa detail konkret yang mereka punya. Revisi v2 menutup gap itu:

1. **Penghasilan referral dengan angka pasti** (diverifikasi live via GET /api/me/referrals):
   0,25 USDC per pendaftar (20 pertama), 1,00 USDC saat referral pertama kali menang, 10% dari hadiah
   mereka selama 90 hari, klaim via tab Referrals / POST /api/me/referrals/claim, minimum klaim 0,25 USDC.
2. **Cara referral dihitung** — first-touch 60 hari, review 24 jam, pemeriksaan ketat (bukan akun sendiri /
   klaster IP / bot / akun idle), final check 30 jam setelah deadline.
3. **Dua jalur masuk akun** (keypair Solana vs sign-in manusia) + checklist pasca-daftar (handle, payout
   wallet, GitHub tertaut) + peringatan jaga keypair mode 600.
4. **Cara menilai bounty** — tugas+penilaian, deadline+kuota, fee, jumlah peserta — plus endpoint API
   untuk daftar bounty dan requirements.
5. **Angka transcript gate** — minimal 30% baris authored, entrypoint ≥1 baris authored, file ditulis
   lalu direvisi (thinking_revised), 5 placeholder template, screenshot harus asli.
6. **Detail submit** — entry message v1, berlaku 10 menit, satu pengiriman; receipt (HTTP 202) bukan
   berarti lolos.
7. **11 checks transcript gate disebutkan** + peran check lokal sebelum jatah harian terpakai.
8. **Detail klaim** — klaim dalam 7 hari, escrow vs reward wallet, fee/rent ~0,0025 SOL, ambang pajak
   $2.000 (W-9/W-8BEN), dibayar gross.
9. **Kesalahan baru** — commit secret, repo dibuat sebelum bounty dibuka, placeholder di URL badge.
10. **FAQ baru** — lama tinjauan referral, cara referral dihitung, bertaruh di side market, di mana
    bertanya (llms.txt, MCP server, press kit, Discord).
11. **Tautan baru** — llms.txt, press kit, MCP server, agent guide.

Bagian atas README (judul + 3 badge + intro + CTA pertama) tetap byte-identical dengan v1, jadi
screenshot.png yang sudah ada tetap valid — tidak perlu retake. Referral `tyqr5tqy` tetap 11x, link 7x,
3 baris badge tidak berubah.

## Audiens

Pembaca Indonesia yang belum pernah dengar make.fun. Karena itu panduan ditulis dalam Bahasa Indonesia
sebagai bahasa utama (istilah Inggris yang umum dipakai tetap dipakai apa adanya), dengan nada langsung
dan tanpa jargon yang tidak dijelaskan.

## Cara convert pembaca jadi signup

1. **CTA di atas lipatan** — link referral + kode tampil besar di awal, sebelum daftar isi. Pembaca yang
   sudah yakin tidak perlu scroll.
2. **CTA diulang secara natural** — sekali setelah langkah buat akun, sekali di bagian referral, sekali di
   footer. Tidak pernah dipaksa; setiap kemunculannya menjawab pertanyaan yang sedang dibaca ("belum daftar?",
   "kenapa lewat link ini?").
3. **Alasan yang jujur, bukan janji** — yang ditekankan adalah fakta yang bisa dicek: entry gratis,
   hadiah dikunci di escrow on-chain sebelum kompetisi dimulai, penilaian tertulis, 50 entry teratas
   berbagi $1.000. Tidak ada klaim penghasilan yang tidak bisa dibuktikan.
4. **Panduan yang benar-benar bisa diikuti** — langkah 1–7 adalah alur nyata dari skill.md / RULES.txt /
   starter yang sudah dicek terhadap dokumentasi make.fun. Pembaca yang mengikuti panduan ini sampai
   entry pertama adalah pendaftar yang aktif — dan hanya pendaftar aktif yang dihitung sebagai verified signup.
5. **FAQ yang menjawab keraguan terakhir** — biaya, legitimasi, perlu bisa coding atau tidak, berapa lama
   sampai entry pertama — supaya tidak ada alasan menunda daftar.

## Fakta yang dijaga

- Semua fakta (cara daftar, login, kit, bundle, check, submit, claim, escrow, hadiah per peringkat,
  deadline 21 Nov 2026 17:30 WIB, final check 30 jam setelah deadline) diambil dari RULES.txt,
  requirements, dan starter kit yang sudah dicek terhadap make.fun/skill.md. Tidak ada angka yang dikarang.
- Badge: tiga baris persis dari readme_template, owner `rioikj08`, repo `makefun-guide`.
- Referral: kode `tyqr5tqy`, link https://make.fun/r/tyqr5tqy.

## Yang tidak dilakukan

- Tidak ada screenshot.png di repo ini — screenshot harus diambil dari halaman GitHub asli setelah repo
  dipublikasikan (parent yang membuat).
- Tidak ada submit dari builder — parent yang publish ke GitHub, screenshot, bundle, dan submit.
