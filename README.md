# Zero Cap – demo aplikácia

**Verejná adresa:** https://piknichek.github.io/zero-cap-demo/  (QR kód na slide: `qr_link.png`)

## Ako to otvoriť lokálne
Dvojklik na `index.html` – je to jeden samostatný súbor (HTML/CSS/JS), netreba inštalovať nič. Kamera funguje na `https://` alebo `localhost`; z `file://` použi „Odfotiť QR“ alebo ručné ID.

## Čo je nové
- **Živé overenie cez eKasa:** po naskenovaní QR alebo zadaní ID (`O-` + 32 znakov) appka zavolá eKasa priamo z prehliadača, načíta položky, rozpozná eko položky podľa kľúčových slov v `CONFIG` (bez ohľadu na diakritiku) a ukáže odznak „✓ Overené naživo cez eKasa“.
- Odmietne vratky, duplicity (v rámci relácie) a bločky staršie ako 30 dní.
- Ak je eKasa nedostupná alebo ID neexistuje, appka to jasne povie a ponúkne **demo bločky** (fungujú offline).
- **Skenovanie QR:** natívny `BarcodeDetector`, inak knižnica jsQR (CDN); plus „Odfotiť QR“ z galérie/fotoaparátu. Offline QR (`OKP:…`) sa rozpozná, ale na overenie treba zadať online ID.

## Upozornenie
Endpoint `https://ekasa.financnasprava.sk/mdu/api/v1/opd/receipt/find` je **neoficiálny** – nenašli sme ho v oficiálnej dokumentácii a môže sa kedykoľvek zmeniť alebo zablokovať. Na pilot je potrebné **povolenie Finančnej správy SR** (alebo oficiálny prístup). Podrobnosti: `research2/01_ekasa_overenie.md`.
