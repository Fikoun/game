# Radegastův odkaz — denní NFC geocache

> Krátká denní hra kolem ubytovny — studenti hledají schované NFC tagy.
> Naskenování tagu označí stanoviště v appce a zobrazí hádanku,
> kam jít hledat další skrýš. Po nalezení všech 7 padne finále.

---

## Přehled

- **Kdy:** odpoledne / před večeří, za světla
- **Kde:** kolem Penzionu Janoštík + nejbližší okolí (rádius ~100–200 m)
- **Stanovišť:** 7 NFC tagů schovaných po vesnici (hřiště, krámek, lavičky, sloupek…)
- **Doba hry:** cca 25–35 min na tým
- **Téma:** valašský folklór — Radegast schoval znamení kolem ubytovny

---

## Herní princip

1. Tým dorazí ke schovanému NFC tagu a naskenuje ho mobilem.
2. Appka **rovnou označí stanoviště splněné** (rozsvítí ho v heptagonu) a zobrazí **hádanku** popisující, kde najdou další skrýš.
3. Tým rozluští hádanku, jde na další místo, naskenuje další tag.
4. **Pořadí návštěvy je libovolné** — hinty jdou v kruhu 1 → 2 → … → 7 → 1, ale finále padne až po všech 7 (v jakémkoli pořadí).
5. **Různé starty pro různé týmy** — pedagog řekne každému týmu, kde začít (např. tým A: u hřiště, tým B: u krámku). Tím se vyhne frontám u stejného tagu.
6. Po nalezení všech 7 znamení appka zobrazí **finále** — sejdou se s pedagogem a vyřknou, kdo byl Radegast.

---

## NFC tagy

Každý tag = URL na nasazenou appku s parametrem `?p=N` (číslo stanoviště). Pořadí 1–7 určuje cyklus hintů (po N následuje N+1).

| # | Místo | URL na tag |
|---|-------|------------|
| 1 | **Most** (cedule 10 tun max, řeka pod ním) | `https://fikoun.github.io/game/?p=1` |
| 2 | **Školka** | `https://fikoun.github.io/game/?p=2` |
| 3 | **Basketbalové hřiště** | `https://fikoun.github.io/game/?p=3` |
| 4 | **Prodejna frgálů** — *foto úkol se senem co visí venku* | `https://fikoun.github.io/game/?p=4` |
| 5 | **Zastávka autobusu** | `https://fikoun.github.io/game/?p=5` |
| 6 | **Zavřená zahrada** (cedule vedou tam, kde žádná zahrada není) | `https://fikoun.github.io/game/?p=6` |
| 7 | **Jídelna** (uvnitř ubytovny) | `https://fikoun.github.io/game/?p=7` |

> Foto úkol je v hintu po basketbalu (HINTS[3]). Tým, který by frgály scanoval jako poslední (a tedy viděl finále místo hintu), je na fotku upozorněn v `FINAL_MSG`.

---

## Hádanky / hinty

V `index.html` najdi pole `HINTS` a doplň `text` a `emoji` pro každé pole. `HINTS[N]` = hint, který se zobrazí **po naskenování stanoviště N** a popisuje DALŠÍ skrýš v kruhu (N+1; po 7 následuje 1).

```js
const HINTS = [
  null,
  { emoji: '🎠', text: 'Tam, kde si hraje ten nejmenší.' },           // po 1 → na 2
  { emoji: '🏪', text: 'Kde svítí cedule, i když je zavřeno.' },     // po 2 → na 3
  { emoji: '🌳', text: '_doplnit hádanku na 4_' },                    // po 3 → na 4
  …
];
```

Tip na styl hádanek — krátké, hravé, místně specifické. Pro IT/IT-themed čvrť můžeš použít drobný cipher v textu (binárka, Caesar) nebo zůstat u prostého rébusu.

---

## Příběhový rámec (úvod pedagoga)

> Dávní Valaši věřili, že Radegast, strážce hor a hojnosti, neukryl svůj odkaz
> jen v lese kolem Radhoště — pár znamení rozesel i kolem hospod a vesnic.
> Sedm fragmentů jeho moudrosti je rozeseto i tady, kolem naší ubytovny.
> Najděte je, rozluštěte hádanky a Radegast vás přijme.

---

## Technické poznámky

- **Tagy:** NTAG213/215/216, URL `?p=1` až `?p=7`
- **Marking:** scan = okamžité označení stanoviště + zobrazení flash karty s hintem (žádné kódy k zadávání)
- **Progres** se ukládá do `localStorage` (jeden mobil = jeden tým); tlačítko *začít znovu* dole vymaže
- **Finále** se spustí automaticky, jakmile progres dosáhne 7 (libovolné pořadí)

### Checklist
- [ ] Otestovat čtení tagů na 2–3 mobilech (iPhone i Android)
- [ ] Schovat tagy nenápadně, ale ne pod kov a ne moc nízko (NFC dosah ~2 cm)
- [ ] Doplnit hinty 3→4 až 7→1 v `HINTS` podle finálního rozmístění
- [ ] Připravit rozdělení týmů + startovací stanoviště (1–7)

---

## Stav

- [x] Koncept hry + UI heptagon
- [x] Denní pivot, scan = auto-mark + hint
- [x] Cyklické pořadí + různé starty týmů
- [ ] Vybrat 7 míst kolem ubytovny + nalepit tagy
- [ ] Doplnit hinty 3→4 … 7→1 v `index.html`
- [ ] Realizace
