# Radegastův odkaz — večerní NFC hra

> Večerní orientačně-vědomostní hra pro třídní výlet 2.A do Rožnova pod Radhoštěm.
> Studenti procházejí lesní stezku za ubytovnou, hledají NFC tagy a luští IT hádanky.

---

## Přehled

- **Kdy:** večer po večeři (středa 24. 4.), po setmění
- **Kde:** lesní stezka za ubytovnou (Penzion Janoštík, Rožnov p. R.)
- **Délka trasy:** ~1,5 km (včetně otočky na altánek)
- **Stanovišť:** 7 NFC tagů + sběrný bod na cestě (bez NFC)
- **Doba hry:** cca 40–50 min na tým
- **Téma:** valašský folklór — Radegast, strážce hor a hojnosti
- **Obsah tagů:** navigační varování pro další úsek trasy + jeden foto úkol v altánku

---

## Herní princip

Studenti jdou stezkou a na každém ze 7 stanovišť najdou NFC tag = "znamení Radegastovo".
Tag otevře v mobilu webovou appku, která rozsvítí daný bod v heptagonu a zobrazí
**varování / instrukci pro další úsek** (kam jít, kde pozor na vodu, jak nepřehlédnout fáborek).

Na **rozcestníku (3. stanoviště)** stojí kolegyně-strážkyně. Pošle skupinku na otočku k **altánku
(4. stanoviště)**, kde je foto úkol — společné foto skupinky. Pak se vrací zpět k rozcestníku
a kolegyně je pouští dolů.

Poslední (7.) NFC bod je nad lesní cestou. Po jeho načtení appka zobrazí **finální úkol**:
ukázat pedagogovi fotku z altánku a vyřknout, kdo byl Radegast. Pedagog stojí dole na cestě
a sbírá příchozí skupinky — sběrné místo už NFC nemá.

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
- **Obsah:** URL na nasazenou appku s parametrem `?t=XXXX` (4-místný kód stanoviště)
- **Záloha při výpadku NFC:** v appce je "?" tlačítko → nouzové volání na pedagoga + ruční zadání 4-místného kódu (pedagog ho po telefonu nadiktuje)
- **Kódy stanovišť (drž v tajnosti):** 1=7421, 2=3058, 3=8164, 4=2935, 5=6072, 6=4819, 7=5293
- **Pedagog tel:** doplnit do `EMERGENCY_TEL` v `index.html` (zatím placeholder `+420XXXXXXXXX`)

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

## Stanoviště (reálná trasa)

Trasa za penzionem do lesa, smyčka přes vrchol a altánek, návrat dolů na lesní cestu.

| # | Místo (NFC) | Co tag řekne (varování pro další úsek) |
|---|-------------|----------------------------------------|
| 1 | Odbočka do lesa (~100 m od startu) | Doleva z cesty, po staré kolejnici cca 300 kroků k vrcholu |
| 2 | Vrchol kolejnice | Ostrá doleva, dál po vrstevnici (neklesat / nestoupat) |
| 3 | Rozcestník — **kolegyně** | Poslech kolegyni, pošle skupinu na altánek (otočka) |
| 4 | Altánek | **Foto úkol:** společné foto skupinky (drží se pro finále). Pak zpět k rozcestníku |
| 5 | Dva pařezy | Mírně nahoru, fáborky lehce matoucí. **Pozor: malý potůček překročit** |
| 6 | Doleva dolů (fáborek) | Klesání doleva, dál po fáborcích ke světlině |
| 7 | Nad mýtinou | Sejít přesně dolů na lesní cestu — tam čeká pedagog. Appka spustí **finální úkol** (ukázat fotku + vyřknout, kdo byl Radegast) |
| — | Lesní cesta (sběr) | Pedagog sbírá skupinky, bez NFC |

> Pozn.: pořadí tokenů v `index.html` (`TOKENS`) odpovídá tomuto číslování 1–7.

---

## Časový odhad

7 NFC + altánková otočka × (3 min hledání + 1 min přečtení varování + 2 min přesun)
+ ~5 min foto úkol ≈ **40–50 min / tým**.
Sběrný bod je dole na lesní cestě, ne u ubytovny — odtud se vrací společně.

---

## Stav

- [x] Koncept hry
- [x] Příběhový rámec
- [x] Trasa prošlá a zaměřená (7 NFC bodů)
- [x] Texty stanovišť v appce (navigace + finální úkol)
- [ ] Nalepit / zafixovat NFC tagy na trase
- [ ] Realizace (večer)