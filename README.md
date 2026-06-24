# Radegastův odkaz — denní NFC geocaching s IT šiframi

> Krátká denní hra kolem ubytovny — studenti hledají schované NFC tagy
> a po naskenování řeší jednoduchou IT šifru, jejíž řešení (4-místný kód)
> zadají do appky a dostanou nápovědu k další skrýši.

---

## Přehled

- **Kdy:** odpoledne / před večeří, za světla
- **Kde:** kolem Penzionu Janoštík + nejbližší okolí (rádius ~100–200 m)
- **Stanovišť:** 7 NFC tagů schovaných po vesnici (hřiště, krámek, lavičky, sloupek…)
- **Doba hry:** cca 30–40 min na tým
- **Téma:** valašský folklór — Radegast schoval znamení nejen v lese, ale i kolem hospody
- **Obsah tagů:** každý tag otevře v appce **IT šifru** — výsledek (4 cifry) zadají do appky a vidí hint kam dál

---

## Herní princip

1. Tým dorazí ke schovanému NFC tagu, naskenuje ho mobilem.
2. Appka otevře **šifrovací kartu** pro dané stanoviště (cipher + pomocná tabulka přímo v appce, nic na papíře).
3. Tým šifru vyřeší → vyjde 4-místný kód.
4. Kód zadají na téže kartě → appka rozsvítí stanoviště v heptagonu a ukáže **nápovědu kam jít dál** (text + emoji).
5. Po splnění všech 7 (v libovolném pořadí) padne **finále** — sejdou se s pedagogem a vyřknou, kdo byl Radegast.

**Cyklický postup** (anti-fronta): hinty jdou v kruhu 1 → 2 → … → 7 → 1. Každému týmu přidělí pedagog **jiné startovací stanoviště**, takže nikdo netlačí u stejného tagu.

**Záloha při výpadku NFC:** v pravém horním rohu je "?" tlačítko → nouzové volání pedagogovi + ruční zadání 4-místného kódu (pedagog ho po telefonu nadiktuje).

---

## Příběhový rámec (úvod pedagoga)

> Dávní Valaši věřili, že Radegast, strážce hor a hojnosti, neukryl svůj odkaz
> jen v lese kolem Radhoště — pár znamení rozesel i kolem hospod a vesnic,
> kde Valaši odpočívali. Sedm fragmentů jeho moudrosti je rozeseto i tady,
> kolem naší ubytovny. Najděte je, rozluštěte, a Radegast vás přijme.

---

## Stanoviště (šifry)

Šifry léčebně lehké (1–2 min každá), zaměřené na základní IT převody. Pomocné tabulky se zobrazí přímo v appce.

| # | Typ šifry | Zadání v appce | Kód |
|---|-----------|----------------|-----|
| 1 | Binárka → desítkově | `0111 0100 0010 0001` | `7421` |
| 2 | Hex → ASCII cifry | `33 30 35 38` | `3058` |
| 3 | Morseovka číslic | `---..   .----   -....   ....-` | `8164` |
| 4 | Reverze řetězce | `5392 → ?` | `2935` |
| 5 | Pseudokód | `x=6; x*=2; x+=1000; y=x*6; print(y)` | `6072` |
| 6 | HTML entity | `&#52;&#56;&#49;&#57;` | `4819` |
| 7 | Caesarova šifra (cifry, posun −3 mod 10) | `8526 → ?` | `5293` |

> **Tajné — pro pedagoga, nepouštět studentům.** Kódy jsou zároveň fallback do helpu (zadáš po telefonu).

---

## NFC tagy — co na ně nahrát

Každý tag = URL na nasazenou appku s parametrem `?p=N` (číslo stanoviště, **ne kód**).

| # | Stanoviště (umístění zvolí pedagog) | URL na NFC tag |
|---|--------------------------------------|----------------|
| 1 | _doplnit_ | `https://fikoun.github.io/game/?p=1` |
| 2 | _doplnit_ | `https://fikoun.github.io/game/?p=2` |
| 3 | _doplnit_ | `https://fikoun.github.io/game/?p=3` |
| 4 | _doplnit_ | `https://fikoun.github.io/game/?p=4` |
| 5 | _doplnit_ | `https://fikoun.github.io/game/?p=5` |
| 6 | _doplnit_ | `https://fikoun.github.io/game/?p=6` |
| 7 | _doplnit_ | `https://fikoun.github.io/game/?p=7` |

> Pozor: `?p=N` otevře šifru, ne kód — student musí šifru vyřešit, aby stanoviště označil.

---

## Nápovědy "kam dál" (v appce)

Po vyřešení stanoviště N appka zobrazí hint na další v kruhu. **Doplň v `index.html` v poli `HINTS`** podle finálního rozmístění tagů:

| Z → na | Hint (emoji + text) |
|--------|---------------------|
| 1 → 2 | 🎠 "kde si hraje ten nejmenší" |
| 2 → 3 | 🏪 "kde svítí cedule, i když je zavřeno" |
| 3 → 4 | _doplnit_ |
| 4 → 5 | _doplnit_ |
| 5 → 6 | _doplnit_ |
| 6 → 7 | _doplnit_ |
| 7 → 1 | _doplnit_ (cyklus se uzavírá) |

---

## Technické poznámky k NFC tagům

- **Typ tagů:** lepící NTAG213/215/216 (čte je většina mobilů)
- **Obsah:** URL `https://fikoun.github.io/game/?p=N` (N = 1–7)
- **Pedagog tel:** doplnit `EMERGENCY_TEL` v `index.html` (zatím placeholder `+420XXXXXXXXX`)

### Checklist pro realizaci
- [ ] Otestovat čtení tagů na 2–3 různých mobilech (iPhone i Android)
- [ ] Schovat tagy ne moc nápadně, ale ne pod kov a ne moc nízko (NFC dosah ~2 cm)
- [ ] Voděodolnost — obalit izolepou / zatavit do fólie
- [ ] Připravit rozdělení týmů + jejich startovací stanoviště (1–7)
- [ ] Doplnit `EMERGENCY_TEL` v `index.html` na vlastní číslo
- [ ] Doplnit hinty 3→4, 4→5, 5→6, 6→7, 7→1 v `HINTS` podle finálního rozmístění

### Organizace týmů
- 2–7 týmů, každý startuje na **jiném** stanovišti (žádné fronty u stejného tagu)
- Postup cyklicky 1→2→…→7→1; finále se spustí po splnění všech 7 (v jakémkoli pořadí)
- Sraz po skončení u pedagoga (známé místo)

---

## Časový odhad

7 stanovišť × (3 min hledání + 1–2 min šifra + 1–2 min přesun) ≈ **30–40 min / tým**.

---

## Stav

- [x] Koncept hry
- [x] Pivot na denní geocaching kolem ubytovny
- [x] 7 IT šifer + appka (šifrovací karty, helper tabulky, input)
- [x] Cyklické pořadí + různé starty týmů
- [ ] Vybrat 7 míst kolem ubytovny + nalepit NFC tagy
- [ ] Doplnit hinty (3→4, 4→5, …, 7→1) v `index.html`
- [ ] Doplnit `EMERGENCY_TEL`
- [ ] Realizace
