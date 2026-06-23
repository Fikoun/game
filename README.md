# Radegastův odkaz — večerní NFC hra

> Večerní orientačně-vědomostní hra pro třídní výlet 2.A do Rožnova pod Radhoštěm.
> Studenti procházejí lesní stezku za ubytovnou, hledají NFC tagy a luští IT hádanky.

---

## Přehled

- **Kdy:** večer po večeři (středa 24. 4.), po setmění
- **Kde:** lesní stezka za ubytovnou (Penzion Janoštík, Rožnov p. R.)
- **Délka trasy:** ~1,5 km
- **Stanovišť:** 8 (NFC tagy, rozestup ~200 m)
- **Doba hry:** cca 45–55 min na tým
- **Téma:** valašský folklór — Radegast, strážce hor a hojnosti

---

## Herní princip

Studenti jdou stezkou nahoru a na každém stanovišti najdou NFC tag = "znamení Radegastovo".
Každý tag obsahuje IT hádanku (binárka, Caesarova šifra, kus pseudokódu…) a nápovědu
k dalšímu stanovišti (řetězená trasa / linked list).

Na **vrcholu** je pedagog v roli **strážce / poutníka**. Vyslechne rozluštěný vzkaz,
a když tým uspěje, "prozradí cestu dolů" + dá klíč k závěrečné hádance řešené cestou zpět.

Dole na ubytovně se týmy sejdou a hra se vyhodnotí.

---

## Příběhový rámec (text pro úvod / pedagoga na vrcholu)

> Dávní Valaši věřili, že Radegast, strážce hor a hojnosti, ukryl v lese kolem Radhoště
> svůj odkaz — ne zlato, ale vědění. Kdo dokáže přečíst znamení, která zanechal,
> najde cestu zpět z hor a stane se nositelem jeho moudrosti.
>
> Vy jste se vydali tou cestou. Každé znamení je střípek jeho vzkazu.
> Já jsem jen poutník, který hlídá vrchol — řeknu vám, kudy se vrátit,
> až mi prokážete, že jste znamení rozluštili.

**Poznámka:** konkrétní znění valašských pověstí o Radegastovi se v převyprávěních liší
(směs doložené historie a romantického folkloru 19. stol.) — před čtením nahlas ověřit
v sborníku pověstí / na webu Valašského muzea.

---

## Technické poznámky k NFC tagům

- **Typ tagů:** lepící NTAG213/215/216 (čte je většina mobilů)
- **Obsah:** text přímo na tagu (funguje i bez signálu v lese) — preferováno
- **Alternativa:** URL na statickou stránku (jen pokud chytí mobilní data)

### Checklist pro realizaci
- [ ] Otestovat čtení tagů na různých mobilech (Android auto, iPhone XS+ auto, starší = NFC Tools)
- [ ] Nalepit tagy ve výšce ruky, NE na kov, NE nízko k zemi
- [ ] Voděodolnost — obalit izolepou / zatavit do fólie (počítáme s mokrou variantou)
- [ ] Označit místa reflexní páskou / světélkem (noční hledání)
- [ ] Záloha: u každého stanoviště i QR kód nebo papír se stejnou hádankou
- [ ] Baterky/čelovky povinné, trasa jasně vymezená, pohyb v dvojicích/trojicích
- [ ] Časový limit + jasné místo a čas srazu

### Organizace týmů
- 2–3 týmy s odstupem 5–10 min (zamezí frontám a opisování u tagů)
- Stejné pořadí stanovišť, posunutý start

---

## Stanoviště (obsah tagů)

> TODO: doplnit finální hádanky. Návrh typů níže — provázané jako řetěz,
> dohromady složí Radegastův vzkaz / finální heslo.

| # | Typ hádanky | Obsah tagu | Řešení | Nápověda k dalšímu |
|---|-------------|-----------|--------|--------------------|
| 1 | Binární kód | `01001000 ...` | ? | ? |
| 2 | Caesarova šifra | ? | ? | ? |
| 3 | Hex → text | ? | ? | ? |
| 4 | Pseudokód / vývojový diagram | ? | ? | ? |
| 5 | XOR / klíč z předchozího | ? | ? | ? |
| 6 | Převod soustav | ? | ? | ? |
| 7 | Logická hádanka | ? | ? | ? |
| 8 | Finální složení vzkazu | ? | HESLO | vrchol → pedagog |

---

## Časový odhad

8 stanovišť × (3 min hledání + 2 min hádanka + 2 min přesun) ≈ 55 min / tým.
Poslední stanoviště směřovat blíž k ubytovně (hra se "stahuje" k základně).

---

## Stav

- [x] Koncept hry
- [x] Příběhový rámec
- [ ] Finální obsah tagů (8 hádanek)
- [ ] Test trasy (dnes večer)
- [ ] Realizace (zítra večer)