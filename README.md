# Aidtrace Verified

Build a modern, responsive Web3-themed Education Aid Distribution Transparency platform named "BantuanTrace" using React, TypeScript, Tailwind CSS, and Lucide Icons.



### Design & Theme

- **Vibe**: Professional, clean public-accountability & Web3 aesthetic (Slate dark/light contrast, Indigo/Blue primary accents, Emerald for valid/received badges, Amber for in-progress, Rose for invalid/cancelled badges).

- **Layout**: Top navbar for public pages, collapsible sidebar for Distributor (Penyalur), Recipient (Penerima), and Auditor dashboards.

- **Responsiveness**: Fully optimized for mobile, tablet, and desktop (sidebar on desktop, bottom navigation on mobile).

- **UI language**: Indonesian labels, with loading, empty, and error states on every page.



### Core Concept

Education aid (scholarship / student assistance) disbursement is recorded as a status timeline. Only proof is recorded "on-chain" (simulated Solana devnet): document hash (SHA-256 with random salt), status, timestamp, actor wallet address, and an anonymous disbursement code (e.g., BT-001). Names, ID numbers, documents, and amounts stay "off-chain" in mock data and are never shown on the public verification page.



### Target Roles & Features



1. Public / Auditor (Verifier):

   - Search a disbursement by anonymous Code (e.g., `BT-001`) or SHA-256 Document Hash.

   - Live simulated Web3 scanning effect ("Reading On-Chain Hash...").

   - Verification Result Card showing: Result (SESUAI / TIDAK SESUAI), Code, Current Status, Status Timeline (DIAJUKAN -> DISETUJUI -> DICAIRKAN -> DITERIMA / DIBATALKAN) with timestamp and shortened actor wallet per step, Document Hash, Simulated Block Number, Simulated Tx Signature with "View on Explorer" button (simulated link).

   - "Verify Hash" button: re-hash the current dummy record and compare with the on-chain hash. Include a demo toggle "Simulate tampered record (change 1 character)" that makes the result INVALID.

   - Never display personal data (no names, no NIM/NIK).



2. Distributor (Penyalur) Dashboard:

   - Metric Stats Cards: Total Disbursements, Received, In Progress, Cancelled.

   - Simple chart showing monthly disbursement count trends.

   - Master Disbursement Table with search, status filter, and status badges.

   - "Add New Disbursement" Modal: dummy recipient alias, dummy document upload, auto-generated SHA-256 hash (with salt) and unique code (BT-XXX).

   - Status update buttons (Setujui / Cairkan / Batalkan) that append a new timeline entry with simulated on-chain write and a toast "Recorded to Solana devnet (simulated)".



3. Recipient (Penerima) Dashboard (Default fictional user: "Dimas Prakoso (dummy)", alias code RCP-001):

   - Profile header with quick stats (Total Aid Records, Confirmed Received).

   - Card list of own aid records (e.g., Bantuan Biaya Pendidikan Semester 1, Bantuan Buku, Bantuan Biaya Hidup) with current status badge and mini timeline.

   - "Konfirmasi Terima" button that simulates a wallet signature (a modal that only asks to sign a message, never a transaction) and then sets status to DITERIMA.

   - After confirmation, show a "Bukti Terima" (Receipt Proof) card with a generated QR code, anonymous code, hash, timestamp, and buttons: "Salin Tautan Verifikasi", "Verifikasi On-Chain", "Download Bukti".



4. Master Record List Page (Auditor view):

   - Filterable, searchable, paginated table of all anonymized dummy disbursements (Code, Status, Timestamp, short Hash, Explorer link). No personal data.



5. Landing Page:

   - Hero with bold headline ("Bukti penyaluran bantuan yang bisa kamu periksa sendiri"), quick verification search box on top, value proposition cards (Tidak bisa diubah diam-diam, Data pribadi tetap privat, Bukti terima untuk penerima), and "How It Works" steps (Catat -> Hash -> Catat On-Chain -> Konfirmasi Terima -> Verifikasi).



### Wallet & Roles (Simulated)

- "Connect Wallet" is a mock button that picks a role (Penyalur / Penerima / Auditor) using fake wallet addresses. No real wallet integration.



### Technical & Security Guidelines

- Use React, TypeScript, Tailwind CSS, and lucide-react icons.

- Use mock/dummy data only. Do NOT use real personal data. All names, codes, hashes, block numbers, and amounts are fictional.

- NEVER request wallet private keys, seed phrases, or passwords. Wallet interaction is limited to a simulated "sign message".

- Do NOT put secrets or API keys in the code. Validate all form inputs (client-side) and sanitize rendered output.

- Reusable modular components: Badge, Card, Modal, Table, SearchInput, StatusTimeline, StatCard, QRProofCard.

- Do not add features outside the list above.



### Acceptance Criteria

- Auditor can verify one record in under one minute.

- Changing one character in the dummy record makes verification fail (TIDAK SESUAI).

- Each role only sees its allowed pages.

- No personal data appears on any public page.

- App runs locally with `npm install` and `npm run dev`.

This project was built with [Lovable](https://lovable.dev).

## Build with Lovable

Continue developing this project in the [Lovable editor](https://lovable.dev/projects/547ab9b7-dd85-49db-bcfd-1508b236244e).

- **Ship faster**: describe what you want to build and Lovable handles the code.
- **Stay in sync**: every change made in Lovable is committed straight to this repository.
- **Full ownership**: this code is yours. Push to `main` on GitHub and your changes sync back into Lovable, ready for your next prompt.

## Development

Prefer working locally? You need Node.js and npm — [install with nvm](https://github.com/nvm-sh/nvm#installing-and-updating).

```sh
git clone <this-repository-url>
cd <repository-name>
npm i
npm run dev
```
