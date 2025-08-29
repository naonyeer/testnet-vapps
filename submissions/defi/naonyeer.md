vApp Submission: LP Streak Attest
Verification

github_username: naonyeer

discord_id: 458584863885230083

timestamp: 2025-08-29

Developer

Name: naonyeer

GitHub: @naonyeer

Discord: @deezeth

Experience: DeFi user & testnet grinder; biasa bikin bot/task automations, integrasi wallet, dan simple dashboards.

Project
Name & Category

Project: LP Streak Attest

Category: defi

Description

Problem: Banyak program DeFi ingin memberi insentif ke liquidity provider yang konsisten (bukan hit-and-run), tapi sulit membuktikan “konsistensi” lintas protokol/chain tanpa minta data sensitif.
What it does: LP Streak Attest membuat attestation terverifikasi bahwa suatu wallet menjaga posisi LP ≥ N hari berturut-turut atau ≥ ambang minimum. Attestation ini portable—bisa dipakai protokol lain untuk fee-rebate, allowlist, atau bonus rewards—tanpa membocorkan jumlah LP tepatnya.

SL Integration

Attestations: Terbitkan verifiable attestations berisi “LP ≥ threshold” + “durasi streak (hari/minggu)”.

Proofs: Mulai dari bukti deterministik berbasis snapshot; rencana upgrade ke threshold/range proof (membuktikan ≥ X tanpa nilai spesifik) saat primitif ZK/SL yang relevan tersedia.

Verification: dApps pihak ketiga memanggil verifier (SDK/CLI SL) untuk mengecek keabsahan attestation sebelum memberi insentif.

Technical
Architecture (high level)

Indexer Worker: baca posisi LP dari subgraph/RPC (mis. Uniswap-v2/v3 style) pada interval terjadwal → hitung streak & threshold.

Attestation Service: ketika syarat terpenuhi, generate dan sign SL attestation untuk wallet.

Verifier API / SDK: endpoint ringan untuk dApps memverifikasi attestation via Soundness Layer.

Web App (Dashboard): konek wallet → lihat progres streak, minta attestation, dan ekspor/claim di protokol partner.

Stack

Frontend: React + Wagmi/Viem

Backend: Node.js (TypeScript)

Blockchain: EVM testnet (Sepolia/OP-Sepolia) + Soundness Layer

Storage: Postgres (ringan) untuk cache; metadata attestation ke IPFS/WALRUS bila perlu

Features

F1. Streak Tracker: hitung durasi LP harian/mingguan per pool.

F2. Threshold Attestation: terbitkan attestation “LP ≥ X selama Y hari”.

F3. Partner Verifier: lib kecil untuk protokol lain mengecek attestation dan memberikan fee rebate / allowlist / bonus.

Timeline
PoC (2–4 weeks)

Integrasi pembacaan posisi LP untuk 1–2 DEX testnet

Generate & verifikasi SL attestation dasar

Minimal UI untuk connect wallet & request attestation

MVP (4–8 weeks)

Multi-pool & multi-chain support

Verifier SDK + halaman demo claim rewards

Otomasi rotasi/snapshot + monitoring, uji beban ringan

Innovation

Portable LP reputation: reputasi “konsistensi LP” bisa dibawa lintas protokol tanpa KYC.

Privacy-aware: gunakan attestation/threshold, tanpa buka nilai LP persis.

Sybil-resistant insentives: protokol memberi hadiah pada sustained liquidity, bukan farming sesaat.

Contact

Preferred: Discord DM (ID: 458584863885230083)

Updates: issue/PR di repo project + channel build di Soundness Discord.

Checklist before submitting

 All fields completed

 GitHub username matches PR author (naonyeer)

 SL integration explained (attestation + verifier, optional threshold proof)

 Realistic timeline (PoC 2–4w, MVP 4–8w)
