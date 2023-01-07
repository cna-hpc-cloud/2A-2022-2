# Tujuan Akhir 
Menyusun model arsitektur yang mendukung real-time collaboration, mempunyai security layer, dan terdistribusi.

## Tech
- IPFS (untuk aspek distributed storage layer)
- WebRTC (untuk aspek real-time communication layer)
- Yjs (untuk askpek collaborative)
- ??? (aspek distributed security)

## Pertanyaan awal

1. Arsitektur real-time kayak gimana? (WebRTC)
2. Arsitektur collaborative software kayak gimana? (Data struktur & Merging)
3. Security-nya kayak gimana? (Authorization, validation(ex: file integrity))
4. Bagaimana performancenya? (Apa perlu dibandingin sama yang centralized? Tanya ke Pa Hilman)

## Pertanyaan kalo dipindah ke konsep terdistribusi: (intinya cari yg ekuivalen)

1. Bagaimana hubungan antar nodenya dalam real-time yg terdistribusi? Data exchangenya gimana? Prioritasnya apa, lebih ke efficiency, robusteness, scalability?
2. Collaborative proses signaling? How do we determine source of truth to maintain consistency and/or reliability? Gimana caranya minimize latency antar node (pengguna)? Data struktur yg di-share bentuknya kayak gimana, dan kenapa data struktur tsb dipilih? Metode untuk merge conflict-nya kayak gimana?
3. Dari segi security, gimana ngatur proses authorizationnya? gimana ngebuat flow access controlnya? gimana cara ngebagi distribusi autohrization rights ke masing masing node?

## Wajib di-test
1. Performance: load testing
2. Consistency: ???
3. Communication: WebRTC Latency, integrity(?)

## Possible problems
1. Asymmetric NAT (NAT Traversal Method)  
   Apakah bisa memanfaatkan protokol IPFS? https://blog.ipfs.tech/2021-02-03-js-ipfs-0-54/#%E2%86%94%EF%B8%8F-nat-upnp-hole-punching
   - Router harus support `UPnP`

   Diskusi:
   - https://discuss.libp2p.io/t/how-nat-traversal-and-hole-punching-work-in-ipfs/1422/2
   - https://github.com/ipfs/kubo/issues/57
   - https://github.com/ipfs/camp/blob/master/DEEP_DIVES/40-better-nat-traversal-so-that-relay-servers-are-a-last-not-first-resort.md

## Aspek Database
1. Ngebuat arsitektur dan implementasi software berbasis peer to peer dengan basis data yang terdistribusi yang memenuhi sifat real time dan local first menggunakan IPFS

