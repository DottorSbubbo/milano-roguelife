# MILANO ROGUELIFE — Game Design Document

## Panoramica
Roguelike a turni con meccanica di cattura e potenziamento di creature chiamate **ROT**. Run infinite con difficoltà crescente. Nessuna fine — si va avanti finché l'AI non diventa troppo forte.

---

## I ROT (Creature)

Le creature si chiamano **ROT** (non Pokémon).

### Rot Shiny
- Probabilità **1%** di apparire (come starter o nel negozio)
- Aspetto: saturazione moderatamente aumentata (non esagerata) + leggermente più grande in battaglia
- Stats: **+10% a tutte le stat base**

---

## 8 TIPI

| Tipo | Batte | Perde contro |
|---|---|---|
| **NORMIE** | SCHIZO | PSYCHO |
| **SCHIZO** | PSYCHO | NORMIE |
| **PSYCHO** | NORMIE | SCHIZO |
| **TROLL** | VAPE | CRYPTO |
| **CRYPTO** | TROLL | MOG |
| **MOG** | CRYPTO | TIPA |
| **VAPE** | MACHO | TROLL |
| **MACHO** | TRANS | VAPE |
| **TRANS** | TIPA | MACHO |
| **TIPA** | MOG | TRANS |
| **BASED** | BASED | BASED |

### Moltiplicatori danno
- Super efficace: x2
- Neutro: x1
- Non molto efficace: x0.5
- **STAB**: x1.5 se la mossa è dello stesso tipo del Rot che la usa

### Resistenze
Ogni Rot riceve x0.5 danno dalle mosse del proprio tipo e dalle mosse del tipo contro cui è forte.
Esempio: NORMIE resiste le mosse tipo NORMIE e le mosse tipo SCHIZO (perché NORMIE batte SCHIZO).

**Eccezione — BASED:** è l'unico tipo senza resistenze. Non resiste né alle mosse BASED né ad altro. Le mosse BASED non hanno moltiplicatori di tipo contro nessun avversario.

---

## 16 ROT — Stat Base e Mosse

### Formula danno (stile Pokémon)
`Danno = ((2×Livello/5 + 2) × Potenza × Attacco/Difesa) / 50 + 2) × 3`

### Critico
- Probabilità base: **10%**
- Moltiplicatore: **x1.5**

### Elusività
- Probabilità base: **0%**
- Aumentabile con Drugs (SAMBUCHINO)

### Stadi stat
Ogni stadio modifica una stat del **±15%**, max **±3 stadi**

| Stadi | Modifica |
|---|---|
| -3 | -45% |
| -2 | -30% |
| -1 | -15% |
| 0 | nessuna |
| +1 | +15% |
| +2 | +30% |
| +3 | +45% |

---

### ROT #01 — MIKEY TREMBOLONE
**Tipo:** MOG
**Stat base:** HP 50 / ATK 80 / SP.ATK 30 / DEF 60 / SP.DEF 30 / SPD 50 (TOT 300)
**Mossa unica:** SIRINGONE — Fisico, 50 danni, 30% di applicare AVVELENATO
**Talento (liv 50):** STOCK ILLIMITATO — Il cap massimo di stack AVVELENATO applicabili ai nemici aumenta di +2 ogni 50 livelli (liv 50: 3 stack, liv 100: 5 stack, liv 150: 7 stack, liv 200: 9 stack...) infinito oltre il liv 200

### ROT #02 — CRYPTOBISMOL
**Tipo:** CRYPTO
**Stat base:** HP 40 / ATK 30 / SP.ATK 80 / DEF 30 / SP.DEF 60 / SPD 60 (TOT 300)
**Mossa unica:** REDDIT — Speciale, 50 danni, 30% di applicare TASCHE BUCATE
**Talento (liv 50):** AIRDROP — CRYPTOBISMOL inizia ogni battaglia con 2 buff casuali già attivi. Rende TASCHE BUCATE stackabile: ogni stack aggiuntivo aumenta del 20% il gold generato dal danno ricevuto, e ogni stack infligge danno al ROT afflitto pari al gold generato tramite TASCHE BUCATE in quel turno. Scaling: +2 buff casuali ogni 50 livelli (liv 50: 2 buff, liv 100: 4 buff, liv 150: 6 buff, liv 200: 8 buff...) infinito oltre il liv 200

### ROT #03 — BIG MAC
**Tipo:** NORMIE
**Stat base:** HP 90 / ATK 40 / SP.ATK 60 / DEF 60 / SP.DEF 40 / SPD 10 (TOT 300)
**Mossa unica:** MENU LARGE — Speciale, 50 danni, 30% di applicare COLLASSO
**Talento (liv 50):** EXTRA LARGE — Ogni volta che subisce un colpo restituisce il 10% del danno ricevuto come danno all'attaccante, e ha 5% di probabilità di applicare COLLASSO all'attaccante. Scaling: entrambi +10% danno restituito e +5% probabilità COLLASSO ogni 50 livelli (liv 50: 10% danno / 5% COLLASSO, liv 100: 20% / 10%, liv 150: 30% / 15%, liv 200: 40% / 20%...) infinito oltre il liv 200

### ROT #04 — CHEESECAKE
**Tipo:** VAPE
**Stat base:** HP 50 / ATK 40 / SP.ATK 60 / DEF 40 / SP.DEF 50 / SPD 60 (TOT 300)
**Mossa unica:** SVAPO DIESEL — Speciale, 50 danni, 30% di applicare STRAFATTO
**Talento (liv 50):** MIXOLOGIA — Per ogni ROT NEMICO in campo con status STRAFATTO, CHEESECAKE ottiene +50% a tutte le stats eccetto HP. Scaling: +50% ogni 50 livelli aggiuntivi per ogni ROT nemico STRAFATTO (liv 50: +50% per nemico STRAFATTO, liv 100: +100%, liv 150: +150%, liv 200: +200%...) infinito oltre il liv 200

### ROT #05 — LINO STAGNO
**Tipo:** SCHIZO
**Stat base:** HP 60 / ATK 30 / SP.ATK 50 / DEF 70 / SP.DEF 70 / SPD 20 (TOT 300)
**Mossa unica:** NO VAX — Utility, 0 danni, rimuove tutti gli status negativi dalla squadra + scudo 20% HP max a tutti
**Talento (liv 50):** SCUDO MAGGIORATO — Tutti gli scudi applicati da LINO STAGNO sono aumentati del 10%, e il cap massimo di scudo applicabile (normalmente 200% HP) aumenta del 10% aggiuntivo. Scaling: entrambi +10% ogni 50 livelli (liv 50: +10% efficacia / cap 210% HP, liv 100: +20% / cap 220%, liv 150: +30% / cap 230%, liv 200: +40% / cap 240%...) infinito oltre il liv 200. Questo aumento del cap si somma con qualsiasi altro oggetto o effetto che modifica il cap massimo di scudo, come G FUEL

### ROT #06 — TROLLO
**Tipo:** TROLL
**Stat base:** HP 50 / ATK 60 / SP.ATK 50 / DEF 40 / SP.DEF 40 / SPD 60 (TOT 300)
**Mossa unica:** RAGE BAIT — Fisico, 50 danni, 30% di applicare BURNOUT
**Talento (liv 50):** PUMP IT — Ogni volta che un ROT nemico muore in battaglia, TROLLO guadagna +0,5% permanente a tutte le statistiche. Scaling: il bonus per ogni nemico morto aumenta di +0,5% ogni 50 livelli (liv 50: +0,5% per nemico morto, liv 100: +1%, liv 150: +1,5%, liv 200: +2%...) infinito oltre il liv 200. Il bonus si accumula nella run, una battaglia vinta con 3 nemici morti dà fino a 3 volte il bonus per singolo nemico

### ROT #07 — ELONIO MUSCHIO
**Tipo:** PSYCHO
**Stat base:** HP 50 / ATK 70 / SP.ATK 50 / DEF 40 / SP.DEF 40 / SPD 50 (TOT 300)
**Mossa unica:** FIRED! — Fisico, 50 danni, 30% di applicare BRUCIATO
**Talento (liv 50):** FUMO TOSSICO — Il cap massimo di stack BRUCIATO applicabili ai nemici aumenta di +2 ogni 50 livelli (liv 50: 3 stack, liv 100: 5 stack, liv 150: 7 stack, liv 200: 9 stack...) infinito oltre il liv 200

### ROT #08 — BRASATO
**Tipo:** BASED
**Stat base:** HP 60 / ATK 80 / SP.ATK 30 / DEF 50 / SP.DEF 30 / SPD 50 (TOT 300)
**Mossa unica:** MANNAIA MANNAGGIA — Fisico, 40 danni, applica 1 stack FERITE al bersaglio
**Talento (liv 50):** SOTTOVUOTO — FERITE viene applicato sempre con qualsiasi fonte di danno e con qualsiasi mossa usata da BRASATO. Applica 2 stack aggiuntivi di FERITE ogni 50 livelli (liv 50: +2 stack, liv 100: +4 stack, liv 150: +6 stack, liv 200: +8 stack...) infinito. Scaling danno: ogni stack FERITE infligge +10% danno aggiuntivo extra ogni 50 livelli (liv 50: +10%, liv 100: +20%, liv 150: +30%, liv 200: +40%...) infinito oltre il liv 200

### ROT #09 — MOG MOB
**Tipo:** MOG
**Stat base:** HP 50 / ATK 80 / SP.ATK 30 / DEF 70 / SP.DEF 30 / SPD 40 (TOT 300)
**Mossa unica:** CRIMSON MENTONE — Utility, tutta la squadra: -2 stadi Difesa e Difesa Speciale, +2 stadi Attacco e Attacco Speciale
**Talento (liv 50):** CHIN CHECK — Il cap massimo degli stadi applicabili da o su MOG MOB aumenta di +1 ogni 50 livelli (normalmente ±8) (liv 50: ±9, liv 100: ±10, liv 150: ±11, liv 200: ±12...) infinito oltre il liv 200

### ROT #10 — LOGAN FRAUD
**Tipo:** CRYPTO
**Stat base:** HP 40 / ATK 30 / SP.ATK 70 / DEF 30 / SP.DEF 50 / SPD 80 (TOT 300)
**Mossa unica:** RUGPULL — Speciale, 15 danni base +1 danno per ogni Gold in banca
**Talento (liv 50):** EXIT SCAM — Ogni mossa usata da LOGAN FRAUD ottiene potenza aggiuntiva pari al 20% del gold posseduto, sommata alla potenza base prima del calcolo del danno (es. mossa da 50 potenza con 100 gold posseduto diventa 70 potenza). Scaling: +10% gold convertito in potenza ogni 50 livelli (liv 50: +20%, liv 100: +30%, liv 150: +40%, liv 200: +50%...) infinito oltre il liv 200

### ROT #11 — POKE MON
**Tipo:** NORMIE
**Stat base:** HP 70 / ATK 30 / SP.ATK 50 / DEF 50 / SP.DEF 60 / SPD 40 (TOT 300)
**Mossa unica:** TREDICESIMA — Utility, cura tutta la squadra del 25% degli HP massimi di POKE MON
**Talento (liv 50):** WELFARE — Tutte le cure applicate da POKE MON sono aumentate del 10%. Scaling: +10% ogni 50 livelli (liv 50: +10%, liv 100: +20%, liv 150: +30%, liv 200: +40%...) infinito oltre il liv 200

### ROT #12 — SVAPO KINK
**Tipo:** VAPE
**Stat base:** HP 50 / ATK 30 / SP.ATK 70 / DEF 40 / SP.DEF 60 / SPD 50 (TOT 300)
**Mossa unica:** SOFFOCOTTO — Speciale, 30 danni a tutti i nemici contemporaneamente
**Talento (liv 50):** TIRATA LUNGA — Lo status STRAFATTO applicato da SVAPO KINK dura 1 turno extra ogni 50 livelli (liv 50: 1 turno extra, liv 100: 2, liv 150: 3, liv 200: 4...) infinito oltre il liv 200

### ROT #13 — FRANCO
**Tipo:** SCHIZO
**Stat base:** HP 60 / ATK 40 / SP.ATK 60 / DEF 40 / SP.DEF 40 / SPD 60 (TOT 300)
**Mossa unica:** RICICLAGGIO — Speciale, 30 danni, 50% di applicare uno status casuale
**Talento (liv 50):** VITA PAZZA — Finché FRANCO è in campo, tutto il danno inflitto dagli status AVVELENATO e BRUCIATO in battaglia è amplificato del 10%, indipendentemente da chi li ha applicati. Scaling: +10% ogni 50 livelli (liv 50: +10%, liv 100: +20%, liv 150: +30%, liv 200: +40%...) infinito oltre il liv 200

### ROT #14 — USBATTI
**Tipo:** TROLL
**Stat base:** HP 40 / ATK 80 / SP.ATK 30 / DEF 30 / SP.DEF 30 / SPD 90 (TOT 300)
**Mossa unica:** USB-C — Fisico, 80 danni, recoil pari al 20% del danno inflitto al bersaglio, con cap massimo al 20% degli HP massimi di USBATTI per singolo colpo
**Talento (liv 50):** CARICA VELOCE — USBATTI ottiene +5% di elusività permanente (probabilità di schivare attacchi nemici). Scaling: +5% ogni 50 livelli (liv 50: 5%, liv 100: 10%, liv 150: 15%, liv 200: 20%...) infinito oltre il liv 200

### ROT #15 — SEAO
**Tipo:** PSYCHO
**Stat base:** HP 60 / ATK 50 / SP.ATK 70 / DEF 50 / SP.DEF 50 / SPD 20 (TOT 300)
**Mossa unica:** EVASIONE FISCALE — Fisico, 40 danni a tutti i nemici, 50% di perdere 10% dei propri Gold
**Talento (liv 50):** HOLDING — SEAO guadagna +2 gold extra per ogni ROT nemico colpito da EVASIONE FISCALE. Scaling: +2 gold ogni 50 livelli (liv 50: +2g, liv 100: +4g, liv 150: +6g, liv 200: +8g...) infinito oltre il liv 200

### ROT #16 — GIANNI IL PIZZAIOLO SOTTO CASA
**Tipo:** BASED
**Stat base:** HP 70 / ATK 60 / SP.ATK 40 / DEF 60 / SP.DEF 50 / SPD 20 (TOT 300)
**Mossa unica:** CHIACCHIERE DA BAR — Utility, +1 stadio Difesa e Difesa Speciale a tutta la squadra
**Talento (liv 50):** DOC VERACE — GIANNI IL PIZZAIOLO ottiene +5% di resistenza a tutti i tipi (riduzione danno subito). Scaling: +5% ogni 50 livelli (liv 50: 5%, liv 100: 10%, liv 150: 15%, liv 200: 20%...) infinito oltre il liv 200

### ROT #17 — KAMOOM
**Tipo:** TIPA
**Stat base:** HP 60 / ATK 60 / SP.ATK 60 / DEF 50 / SP.DEF 50 / SPD 20 (TOT 300)
**Mossa unica:** BOMBOCLAT — Fisico, 40 danni a un bersaglio, infligge anche il 20% del danno ai ROT nemici adiacenti al bersaglio (solo se posizionati accanto)
**Talento (liv 50):** PROLE — Aumenta del 5% il danno di tutti gli attacchi di KAMOOM, incluso il danno ad area, ogni 50 livelli (liv 50: +5%, liv 100: +10%, liv 150: +15%, liv 200: +20%...) infinito oltre il liv 200

### ROT #18 — FUMACAZZI
**Tipo:** TIPA
**Stat base:** HP 50 / ATK 50 / SP.ATK 70 / DEF 40 / SP.DEF 40 / SPD 50 (TOT 300)
**Mossa unica:** FOTUZZA — Fisico, 40 danni, attacca sempre per primo ignorando la velocità di tutti i ROT in campo, 30% di stunnare il bersaglio per il turno
**Talento (liv 50):** PAPARAZZA — Aumenta del 5% ogni 50 livelli la probabilità di applicazione di status/effetti di tutta la squadra alleata (incluse le probabilità dei talenti di altri ROT in squadra, es. se MEDIASET di SILVIO B. ha 30% di duplicare buff/scudo al liv 50, con PAPARAZZA in squadra diventa 35% — non funziona sui colpi critici). Inoltre FUMACAZZI guadagna +10% danno per ogni status negativo presente sulla squadra nemica, scaling +10% ogni 50 livelli aggiuntivi (liv 50: +10% probabilità status squadra / +10% danno per status negativo nemico, liv 100: +15% / +20%, liv 150: +20% / +30%, liv 200: +25% / +40%...) infinito oltre il liv 200

### ROT #19 — DIO PORSCHE
**Tipo:** TRANS
**Stat base:** HP 50 / ATK 80 / SP.ATK 50 / DEF 40 / SP.DEF 30 / SPD 50 (TOT 300)
**Mossa unica:** TRAFFICO MATTUTINO — Fisico, 25 danni, colpisce il bersaglio 2 volte, ogni colpo applica 1 stack di TRAFFICO (cumulabile fino a 4 stack — ogni stack riduce danno inflitto e velocità del ROT afflitto del 5%)
**Talento (liv 50):** INGOMBRANTE — Il cap massimo di stack TRAFFICO applicabili aumenta di +1 ogni 50 livelli, e la riduzione percentuale per stack aumenta del 5% ogni 50 livelli (liv 50: cap 5 stack / -10% per stack, liv 100: cap 6 / -15%, liv 150: cap 7 / -20%, liv 200: cap 8 / -25%...) infinito oltre il liv 200

### ROT #20 — EURO 0
**Tipo:** TRANS
**Stat base:** HP 90 / ATK 50 / SP.ATK 40 / DEF 80 / SP.DEF 30 / SPD 10 (TOT 300)
**Mossa unica:** MICRO PARTICELLE — Speciale, nube di smog che colpisce tutti i ROT nemici contemporaneamente, applica AVVELENATO, BRUCIATO e 1 stack di TRAFFICO a tutti
**Talento (liv 50):** PERMESSO AREA C — Aumenta il cap massimo di stack di AVVELENATO, BRUCIATO e TRAFFICO di +1 ogni 50 livelli, infinito oltre il liv 200

### ROT #21 — ARTMIR
**Tipo:** MACHO
**Stat base:** HP 70 / ATK 70 / SP.ATK 30 / DEF 60 / SP.DEF 40 / SPD 30 (TOT 300)
**Mossa unica:** ALCOLISMO — Utility, ARTMIR ottiene uno scudo pari al 15% dei propri HP totali. Per 3 turni, se un attacco colpirebbe un ROT alleato, viene reindirizzato su ARTMIR invece. Visibile come icona dedicata (manina alzata con dito indice alzato) sopra ARTMIR, con finestra info cliccabile come gli altri status/buff. Non può essere copiato, duplicato o replicato da nessun effetto (es. COLBACCO, talenti di duplicazione) — può esistere un solo ALCOLISMO attivo per squadra contemporaneamente
**Talento (liv 50):** TESTOTERRONE — Aumenta la durata di ALCOLISMO di +1 turno ogni 50 livelli e lo scudo applicato di +10% ogni 50 livelli, infinito oltre il liv 200 (liv 50: 4 turni / +10% scudo, liv 100: 5 turni / +20%, liv 150: 6 turni / +30%, liv 200: 7 turni / +40%...)

### ROT #22 — SILVIO B.
**Tipo:** MACHO
**Stat base:** HP 60 / ATK 40 / SP.ATK 60 / DEF 50 / SP.DEF 50 / SPD 40 (TOT 300)
**Mossa unica:** BUNGA BUNGA — Utility, +1 stadio a tutte le statistiche (ATK SP.ATK DEF SP.DEF SPD) di tutta la squadra alleata
**Talento (liv 50):** MEDIASET — Aumenta passivamente la probabilità di raddoppiare i buff di cura scudo e stadi statistici ottenuti da tutta la squadra alleata, non solo SILVIO B. Scaling: +10% ogni 50 livelli (liv 50: 10%, liv 100: 20%, liv 150: 30%, liv 200: 40%...) infinito oltre il liv 200

---

## MOSSA BASE

**ATTACCO** — disponibile per tutti i Rot dal livello 1
- Tipo: Nessuno (non appartiene a nessun tipo)
- Categoria: Fisico
- Danno: 25
- PP: Infiniti
- Sostituibile: Sì
- Note: non applica STAB, nessun moltiplicatore di tipo, danno sempre neutro x1

---

## MOSSE DI TIPO

Le mosse native dei ROT non sono acquistabili al negozio. Le mosse tipo acquistabili sono solo quelle indicate come "Acquistabile". Le mosse tipo sono fondibili come le mosse COMBO.

### MOG
| Mossa | Tipo | Effetto | Disponibilità |
|---|---|---|---|
| SIRINGONE | Fisico 50 | 30% AVVELENATO | Nativa MIKEY TREMBOLONE |
| CRIMSON MENTONE | Utility | -1 DEF/SP.DEF + +3 ATK/SP.ATK a tutto il team | Nativa MOG MOB |
| COLPO SIGMA | Fisico 40 | — | Acquistabile |
| NO NUT | Speciale 40 | — | Acquistabile |
| SHAKER PROTEICO | Utility | -50% danno nel turno + AVVELENATO a chi attacca, non consecutiva | Acquistabile |

### CRYPTO
| Mossa | Tipo | Effetto | Disponibilità |
|---|---|---|---|
| REDDIT | Speciale 50 | 30% TASCHE BUCATE | Nativa CRYPTOBISMOL |
| RUGPULL | Speciale | 15 danni + 1 danno per ogni gold posseduto | Nativa LOGAN FRAUD |
| BITCOINK | Fisico 40 | — | Acquistabile |
| MEME COIN | Speciale 40 | — | Acquistabile |
| POLYMARKET | Utility | -50% danno nel turno + TASCHE BUCATE a chi attacca, non consecutiva | Acquistabile |

### NORMIE
| Mossa | Tipo | Effetto | Disponibilità |
|---|---|---|---|
| MENU LARGE | Speciale 50 | 30% COLLASSO | Nativa BIG MAC |
| TREDICESIMA | Utility | Cura 20% HP massimi a tutto il team | Nativa POKE MON |
| FOTO DI GRUPPO | Fisico 40 | — | Acquistabile |
| CELEBRITY GOSSIP | Speciale 40 | — | Acquistabile |
| NPC ROUTINE | Utility | -50% danno nel turno + COLLASSO a chi attacca, non consecutiva | Acquistabile |

### VAPE
| Mossa | Tipo | Effetto | Disponibilità |
|---|---|---|---|
| SVAPO DIESEL | Speciale 50 | 30% STRAFATTO | Nativa CHEESECAKE |
| SOFFOCOTTO | Speciale 30 | Colpisce tutti i nemici, 18% STRAFATTO per nemico | Nativa SVAPO KINK |
| TOSSE CRONICA | Fisico 40 | — | Acquistabile |
| SVAPATA | Speciale 40 | — | Acquistabile |
| MISCELATORE | Utility | -50% danno nel turno + STRAFATTO a chi attacca, non consecutiva | Acquistabile |

### SCHIZO
| Mossa | Tipo | Effetto | Disponibilità |
|---|---|---|---|
| NO VAX | Utility | Rimuove status negativi e debuff stadi + scudo 20% HP a tutto il team | Nativa LINO STAGNO |
| RICICLAGGIO | Speciale 30 | 50% di applicare uno status casuale | Nativa FRANCO |
| 2 DIMENSIONI | Fisico 20 | Colpisce 2 volte | Acquistabile |
| 4CHAN THEORY | Speciale 20 | Colpisce 2 volte | Acquistabile |
| POTERI FORTI | Utility | 75% probabilità critico a tutto il team per la battaglia, non consecutiva | Acquistabile |

### TROLL
| Mossa | Tipo | Effetto | Disponibilità |
|---|---|---|---|
| RAGE BAIT | Fisico 50 | 30% BURNOUT | Nativa TROLLO |
| USB-C | Fisico 80 | Recoil 20% del danno inflitto, cap 20% HP massimi | Nativa USBATTI |
| TESCHIO | Fisico 40 | — | Acquistabile |
| GHIGNO MALEFICO | Speciale 40 | — | Acquistabile |
| BAIT SUPREMO | Utility | -50% danno nel turno + BURNOUT a chi attacca, non consecutiva | Acquistabile |

### PSYCHO
| Mossa | Tipo | Effetto | Disponibilità |
|---|---|---|---|
| FIRED! | Fisico 50 | 30% BRUCIATO | Nativa ELONIO MUSCHIO |
| EVASIONE FISCALE | Fisico 30 | Colpisce tutti i nemici, +1 gold per nemico colpito | Nativa SEAO |
| CORPORATE | Fisico 30 | +10 danni per ogni uso consecutivo, si resetta cambiando mossa | Acquistabile |
| HR | Speciale 30 | +10 danni per ogni uso consecutivo, si resetta cambiando mossa | Acquistabile |
| DOGE | Utility | -50% danno nel turno + BRUCIATO a chi attacca, non consecutiva | Acquistabile |

### BASED
| Mossa | Tipo | Effetto | Disponibilità |
|---|---|---|---|
| MANNAIA MANNAGGIA | Fisico 40 | 100% FERITE | Nativa BRASATO |
| CHIACCHIERE DA BAR | Utility | +2 stadi DEF e SP.DEF a tutto il team | Nativa GIANNI IL PIZZAIOLO |
| CHA CHA CHAD | Fisico 20 | 1-4 colpi, probabilità colpi aggiuntivi proporzionale ad ATK | Acquistabile |
| CANNONE SWAG | Speciale 20 | 1-4 colpi, probabilità colpi aggiuntivi proporzionale a SP.ATK | Acquistabile |
| SALSA BASE | Utility | Per 3 turni ogni colpo ha 10% di stunnare il bersaglio, non consecutiva | Acquistabile |

### TIPA
| Mossa | Tipo | Effetto | Disponibilità |
|---|---|---|---|
| BOMBOCLAT | Fisico 40 | 20% danno propagato ai nemici adiacenti | Nativa KAMOOM |
| FOTUZZA | Fisico 40 | Va sempre per prima, 30% stun | Nativa FUMACAZZI |
| GOSSIP | Fisico 40 | — | Acquistabile |
| DRAMA QUEEN | Speciale 40 | — | Acquistabile |
| POSA STUDIATA | Utility | -50% danno nel turno + COLLASSO a chi attacca, non consecutiva | Acquistabile |

### MACHO
| Mossa | Tipo | Effetto | Disponibilità |
|---|---|---|---|
| ALCOLISMO | Utility | Scudo 15% HP + per 3 turni reindirizza attacchi su ARTMIR | Nativa ARTMIR |
| BUNGA BUNGA | Utility | +1 stadio a tutte le stats a tutto il team | Nativa SILVIO B. |
| GOMITATA | Fisico 40 | — | Acquistabile |
| SPACCATA | Speciale 40 | — | Acquistabile |
| ALZATA DI SPALLE | Utility | -50% danno nel turno + BRUCIATO a chi attacca, non consecutiva | Acquistabile |

### TRANS
| Mossa | Tipo | Effetto | Disponibilità |
|---|---|---|---|
| TRAFFICO MATTUTINO | Fisico 25 | Colpisce 2 volte, ogni colpo applica 1 stack TRAFFICO | Nativa DIO PORSCHE |
| MICRO PARTICELLE | Speciale | Colpisce tutti i nemici, applica AVVELENATO BRUCIATO e 1 stack TRAFFICO | Nativa EURO 0 |
| SVOLTA | Fisico 40 | — | Acquistabile |
| RIVELAZIONE | Speciale 40 | — | Acquistabile |
| CAMBIO CORSIA | Utility | -50% danno nel turno + AVVELENATO a chi attacca, non consecutiva | Acquistabile |


---

## STATUS

| Status | Effetto | Durata | Stack | Note |
|---|---|---|---|---|
| **AVVELENATO** | -10% HP per turno | Permanente | No | Non staccabile |
| **STRAFATTO** | 50% chance di mancare | 3 turni | No | Non staccabile |
| **TASCHE BUCATE** | Il ROT afflitto genera il 20% del danno ricevuto come gold per l'avversario (si applica anche sull'attacco che ha applicato il debuff). Se un ROT alleato è afflitto da TASCHE BUCATE il giocatore perde gold equivalente invece di guadagnarlo. | Intero combattimento | No (stackabile solo con talento AIRDROP di CRYPTOBISMOL) | Gold min 0 |
| **BRUCIATO** | -5 HP fissi per turno | Permanente | Sì, max 3 | 3 stack = -15 HP per turno |
| **BURNOUT** | No stessa mossa 2x + doppio PP consumo | 5 turni | No | |
| **COLLASSO** | Salta turno, 50% sveglia per turno | Variabile | No | |
| **FERITE** | +10% danno subito per stack | Permanente | Sì, max 5 | Ogni attacco di Brasato aggiunge 1 stack |
| **STUN** | Blocca l'azione del ROT nel turno corrente se non ha ancora attaccato | 1 turno | No | Come tentennamento Pokémon |

### PP
- Tutte le mosse hanno **10 PP** (tranne ATTACCO base che è infinito)
- PP esauriti = mossa non utilizzabile
- Tutti PP esauriti = Rot non può fare nulla quel turno

### Probabilità status
- Default: **30%** di applicazione salvo eccezioni specifiche

---

## MOSSE NEGOZIO

Le mosse si dividono in COMBO, ATOMICHE e TIPO. Non esiste più il sistema di rarità COMUNE/RARA/ATOMICA. Tutte le mosse COMBO e TIPO possono essere fuse (3 copie identiche = EVO superiore). Le mosse cambiano nome quando evolvono e diventano più forti.

Ogni ROT può avere al massimo 1 copia di una specifica mossa assegnata (non si può avere 2 SHOTTINI sullo stesso ROT).

Le mosse acquistate vanno nel LIBRETTO — un magazzino visibile a destra nella finestra acquisto mosse (i box dei ROT si restringono per fare spazio). Il LIBRETTO ha box rettangolari con il nome della mossa, trascinabili. Trascinando una mossa dal LIBRETTO appare la griglia con SPOSTA sopra e VENDI sotto. Le mosse possono essere trascinate tra LIBRETTO e slot mosse dei ROT liberamente — incluse le mosse EVO. Le mosse uniche base dei ROT sono fisse e non spostabili.

### MOSSE COMBO (fondibili fino a liv 4, cambiano nome ad ogni EVO)
| Mossa | Liv1 | Liv2 | Liv3 | Liv4 |
|---|---|---|---|---|
| SHOTTINI | +1 ATK personale | +1 ATK tutto il team | +2 ATK tutto il team | +4 ATK tutto il team, si casta automaticamente all'inizio battaglia |
| CAFFE | +1 Velocità personale | +1 Velocità tutto il team | +2 Velocità tutto il team | +4 Velocità tutto il team, si casta automaticamente all'inizio battaglia |
| ACTIMEL | +1 DEF personale | +1 DEF tutto il team | +2 DEF tutto il team | +4 DEF tutto il team, si casta automaticamente all'inizio battaglia |
| UNO BRAVO | +1 SP.DEF personale | +1 SP.DEF tutto il team | +2 SP.DEF tutto il team | +4 SP.DEF tutto il team, si casta automaticamente all'inizio battaglia |
| PIPPARE | +1 SP.ATK personale | +1 SP.ATK tutto il team | +2 SP.ATK tutto il team | +4 SP.ATK tutto il team, si casta automaticamente all'inizio battaglia |
| MAKE UP | Scudo 15% HP personali | Scudo 15% HP tutto il team | Scudo 25% HP tutto il team | Scudo 50% HP tutto il team, si casta automaticamente all'inizio battaglia |
| RICCIOLO (ex URCA) | -25% danno durante la prossima fase di attacco (riduce TUTTI gli attacchi della fase) | -50% danno durante la prossima fase di attacco | -50% danno ricevuto per 2 turni | -50% danno ricevuto per 3 turni a tutto il team, si autocasta all'inizio della battaglia, icona ricciolo con numerino turni rimanenti sopra ogni ROT |
| SCHEDINA | +5% gold posseduto | +10% gold posseduto | +50% gold posseduto | +100% gold posseduto, 5% probabilità JACKPOT!! — finestra animata con coriandoli e fuochi d'artificio, poi +50% a tutte le stats dei ROT in battaglia permanentemente |
| TERME | Elimina status negativi inclusi abbassamenti stadi di un ROT | Elimina status negativi inclusi abbassamenti stadi di tutto il team | Elimina status negativi + abbassamenti stadi tutto il team + elimina tutti i buff del team avversario | Elimina status negativi + elimina tutti i buff avversari + raddoppia ogni buff della squadra alleata (aggiunge +1 turno agli effetti a durata) |
| OFFRO IO | Recupera 15% HP di un singolo ROT | Team recupera 15% HP | Team recupera 25% HP | Team recupera 50% HP, l'eccesso si tramuta in scudo |
| SBERLATE | Fisico 20 danni a tutti i nemici | Fisico 40 danni a tutti i nemici | Fisico 60 danni a tutti i nemici + 15% STUN | Fisico 80 danni a tutti i nemici + 25% STUN |
| BORDELLO | Speciale 20 danni a tutti i nemici | Speciale 40 danni a tutti i nemici | Speciale 60 danni a tutti i nemici + 15% STUN | Speciale 80 danni a tutti i nemici + 25% STUN |
| CHINOTTO | +1 stadio elusività personale (1 stadio = 12.5% probabilità schivare) | +1 stadio elusività tutto il team | +2 stadi elusività tutto il team | +4 stadi elusività tutto il team, si casta automaticamente all'inizio battaglia |
| PROVACI | +20% danno subito, restituisce 50% all'attaccante | +20% danno subito, restituisce 80% all'attaccante | +10% danno subito, restituisce 100% all'attaccante | Restituisce 200% del danno ricevuto all'attaccante |
| LANDLORDARE | Team recupera 5% HP per 3 turni | Team recupera 10% HP per 3 turni | Team recupera 15% HP per 4 turni | Team recupera 20% HP per 5 turni, eccesso si tramuta in scudo |
| GRANATALE | +1 stack FERITE a un ROT nemico | 1 stack FERITE a tutto il team nemico | 2 stack FERITE a tutto il team nemico | 4 stack FERITE a tutto il team nemico all'inizio della battaglia automaticamente |

### MOSSE ATOMICHE — da definire

### MOSSE TIPO — fondibili fino a liv 4

**Logica standard fisico/speciale (MOG, CRYPTO, NORMIE, VAPE, TROLL, PSYCHO, TRANS):**
- Liv1: 40 danni
- Liv2: 40 danni + 25% status del tipo
- Liv3: 30×2 danni + 50% status per ogni attacco
- Liv4: 40×2 danni + 75% status per ogni attacco
Status per tipo: MOG=AVVELENATO, CRYPTO=TASCHE BUCATE, NORMIE=COLLASSO, VAPE=STRAFATTO, TROLL=BURNOUT, PSYCHO=BRUCIATO, TRANS=TRAFFICO
CORPORATE e HR seguono la stessa logica PSYCHO (non più meccanica +10/uso consecutivo)

**Logica standard utility (SHAKER PROTEICO, POLYMARKET, NPC ROUTINE, MISCELATORE, BAIT SUPREMO, DOGE, CAMBIO CORSIA):**
- Liv1: -25% danno ricevuto nel turno + 50% di applicare status del tipo
- Liv2: -50% danno + 75% status
- Liv3: -75% danno + 100% status
- Liv4: -75% danno + 100% status applicato a tutto il team nemico nel turno

**SCHIZO fisico (2 DIMENSIONI) e speciale (4CHAN THEORY):**
- Liv1: 40 danni, 25% status negativo casuale (escluso FERITE)
- Liv2: 50 danni, 50% status negativo casuale
- Liv3: 25×2 danni, 100% status per ogni attacco
- Liv4: 25×2 danni a tutto il team nemico, 100% status per ogni attacco

**POTERI FORTI (utility SCHIZO):**
- Liv1: scudo 5% HP a tutto il team + 1 status negativo casuale a 1 ROT nemico casuale
- Liv2: scudo 10% HP + 2 status negativi distribuiti random tra i nemici
- Liv3: scudo 15% HP + 3 status negativi distribuiti random tra i nemici
- Liv4: scudo 20% HP + 2 status negativi a testa per ogni ROT nemico

**BASED fisico (CHA CHA CHAD) e speciale (CANNONE SWAG):**
- Liv1: 1-2 colpi da 20 danni
- Liv2: 1-3 colpi da 20 danni
- Liv3: 1-4 colpi da 20 danni
- Liv4: 1-5 colpi da 20 danni

**SALSA BASE (utility BASED):**
- Liv1: 10% stun sugli attacchi a tutto il team alleato
- Liv2: 20% stun
- Liv3: 50% stun
- Liv4: 65% stun, si autocasta all'inizio della battaglia

**GOSSIP (fisico TIPA):**
- Liv1: 40 danni, 25% di abbassare DEF bersaglio di 1 stadio
- Liv2: 60 danni, 50% di abbassare DEF di 1 stadio
- Liv3: 70 danni, 100% di abbassare DEF di 1 stadio
- Liv4: 80 danni, 100% di abbassare DEF di 3 stadi

**DRAMA QUEEN (speciale TIPA):** stessa logica GOSSIP ma abbassa SP.DEF invece di DEF

**POSA STUDIATA (utility TIPA):**
- Liv1: abbassa DEF e SP.DEF di tutti i nemici di 1 stadio
- Liv2: abbassa di 2 stadi
- Liv3: abbassa di 3 stadi
- Liv4: abbassa di 4 stadi, si autocasta all'inizio della battaglia

**GOMITATA (fisico MACHO):**
- Liv1: 40 danni, 20% di aumentare ATK personale di 1 stadio
- Liv2: 50 danni, 50% di aumentare ATK di 1 stadio
- Liv3: 60 danni, 75% di aumentare ATK di 2 stadi
- Liv4: 80 danni, 100% di aumentare ATK di 3 stadi a tutto il team

**MARTELLO (ex SPACCATA, speciale MACHO):** stessa logica GOMITATA ma su SP.ATK invece di ATK

**ALZATA DI SPALLE (utility MACHO):**
- Liv1: riduce danno fisico e speciale ricevuto del 10% per 2 turni a tutto il team
- Liv2: riduzione 20% per 2 turni
- Liv3: riduzione 35% per 3 turni
- Liv4: riduzione 50% per 3 turni, si autocasta all'inizio della battaglia

---

## DRUGS NEGOZIO

### COMUNI (80%)
| Drug | Effetto |
|---|---|
| FUMELLO | +1 Attacco Speciale permanente |
| COCAINA | +1 Attacco permanente |
| METADINO | +1 Difesa permanente |
| MORFINA | +1 Difesa Speciale permanente |
| METH | +1 Velocità permanente |
| SUCCHINO | +1 HP massimi permanente |
| SABBIONE | -1 Velocità permanente |

### RARE (15%)
| Drug | Effetto |
|---|---|
| CALIFORNIA KUSH | +5 Attacco Speciale permanente |
| COCAONE | +5 Attacco permanente |
| METADONE | +5 Difesa permanente |
| MORFONE | +5 Difesa Speciale permanente |
| BB METH | +5 Velocità permanente |
| SPREMUTA | +5 HP massimi permanente |
| OVERDOSE | Raddoppia tutte le stat, 30% di uccidere istantaneamente il Rot |

### ATOMICHE (5%)
| Drug | Effetto |
|---|---|
| EROINA | +5 a tutte le stat permanente |
| SAMBUCHINO | +1.5% elusività permanente, stackabile |
| CORNETTO | +1% probabilità critico permanente, stackabile |

---

## OGGETTI NEGOZIO

Rarità: COMUNE (60%) · COMBO (35%) · ATOMICO (4%) · APOCALITTICO (1%)

### COMUNE (60%) — non fondibili
| Oggetto | Effetto |
|---|---|
| SPECCHIO | 50% di riflettere uno status negativo all'attaccante |
| SCARPE DA GINNASTICA | Attacca sempre per primo, 1 volta per battaglia |
| ASSICURAZIONE | Se il ROT muore non viene perso, una volta per run |
| PELLE DI ROSPO | Immunità a tutti gli status negativi |
| ZOCCOLI DI LEGNO | Attacca sempre per ultimo, indipendentemente dalla velocità |

### COMBO (35%) — fondibili fino a livello 4
| Oggetto | Liv.1 | Liv.2 | Liv.3 | Liv.4 |
|---|---|---|---|---|
| OCCHIALI DA SOLE | Riduce danno speciale ricevuto 20% | 40% | 50% | 80% |
| GIUBBOTTO ANTIPROIETTILE | Riduce danno fisico ricevuto 20% | 40% | 50% | 80% |
| BILANCIERE | +50% danno fisico inflitto | +83% | +100% | +200% |
| TELESCOPIO | +50% danno speciale inflitto | +83% | +100% | +200% |
| CER8 | Sotto 25% HP cura 20% HP, 1 volta/battaglia | sotto 30% cura 33% | sotto 35% cura 47% | sotto 40% cura 60% + non si può mai morire in un solo colpo (tipo Sturdy, sopravvive con 1 HP) |
| PORTAFORTUNA | +25% probabilità status applicati | +50% | +75% | +100% + quando un malus viene applicato a un nemico viene replicato su tutti gli altri ROT nemici |
| PIGGYBANK | +5 gold a fine turno | +10g | +15g | +30g |
| WELFARE GRATUITO | +25% efficacia cure e scudi | +50% | +100% | +200% |
| COTTA | Restituisce 20% del danno subito | 40% | 60% | 80% |
| AVANZI | Recupera 10% HP massimi a turno | 15% | 20% | 25% (a tutta la squadra alleata) |
| ZECCA COMUNISTA | Drena 50% danno inflitto come HP | 83% | 100% (nessuno scudo) | 150% (eccesso oltre 100% diventa scudo) |
| G FUEL | A fine turno applica scudo pari al 10% degli HP massimi al portatore | 20% | 30% | 50% (e aumenta il cap massimo scudo applicabile al ROT a 300% HP invece del 200% standard) |

### ATOMICO (4%) — non fondibili
| Oggetto | Effetto |
|---|---|
| FENICE | Se il ROT va KO si riprende una volta per battaglia con 25% HP |
| CARTA DI CREDITO | Raddoppia il gold totale guadagnato in ogni battaglia (ricompensa + interessi + altro). Il raddoppio è incluso nel calcolo della riga ALTRO già esistente, senza riga dedicata visibile |
| DIFRATTORE | Trasforma mosse a bersaglio singolo in mosse ad area |
| COLBACCO | Replica cure scudi e buff ricevuti su tutta la squadra |
| CORONAVIRUS | La prima volta in un turno che un qualsiasi status negativo viene applicato a un ROT nemico, lo stesso status viene copiato automaticamente su tutti gli altri ROT nemici in campo |
| GUFO | Il ROT che lo possiede recupera il 100% del danno inflitto dagli status negativi triggerati sui ROT nemici, come HP curati |

### APOCALITTICO (1%) — fondibile fino a livello 4
| Oggetto | Liv.1 | Liv.2 | Liv.3 | Liv.4 |
|---|---|---|---|---|
| SBUBBO | Attacca 2 volte consecutive | 3 volte | 4 volte | 5 volte |

---

## STRUTTURA DELLA RUN

### Inizio
- Il giocatore sceglie 1 Rot tra **3 casuali** come starter (livello 1)

### Progressione battaglie
- Battaglia 1: 1v1 a livello 1
- Battaglia 2: 2v2 a livello 2 (se comprati al negozio)
- Battaglia 3 in poi: 3v3, livello aumenta ogni battaglia vinta
- Max **3 Rot** in squadra

### Fine run
- Run **infinita** — si perde quando tutti e 3 i Rot muoiono nella stessa battaglia
- Record = numero di battaglie sopravvissute

### Permadeath
- Rot morto in battaglia = **perso per sempre** con tutti i suoi upgrade
- Quando un ROT alleato muore gli oggetti equipaggiati vanno automaticamente nel primo slot libero del marsupio — se il marsupio è pieno gli oggetti vengono persi
- Game over se tutti e 3 i Rot muoiono

### Reset ad ogni battaglia
- HP ripristinati al 100%
- PP di tutte le mosse ripristinati a 10
- Tutti gli status negativi e positivi rimossi
- Tutti i modificatori di stadio azzerati
- **Scudo azzerato** — lo scudo persiste tra i turni della stessa battaglia ma si azzera all'inizio di ogni nuova battaglia
- Solo stat base permanenti, oggetti e drugs rimangono

### Sistema buff/debuff visivo
- Quando un ROT è affetto da un buff o debuff di stadio, appare una piccola freccia sopra la barra HP/scudo
- Freccia verso l'alto = buff (stadio aumentato), freccia verso il basso = debuff (stadio diminuito)
- Colori per stat: ATK rosso, SP.ATK viola, DEF blu, SP.DEF verde, SPD ciano
- Buff speciali come POTERI FORTI: freccia verso l'alto giallo/arancione
- Hover sulla freccia apre finestra info a sinistra con descrizione del buff/debuff

### Sistema scudo
- Lo scudo è una barra blu sopra la barra HP verde, stesse dimensioni
- Il danno rimuove prima lo scudo prima di intaccare gli HP
- Lo scudo persiste tra i turni ma si azzera tra le battaglie

---

## SISTEMA ECONOMICO (GOLD)

### Guadagno gold per vittoria
| Turni impiegati | Gold |
|---|---|
| 1 turno | 6 gold |
| 2-3 turni | 4 gold |
| 4+ turni | 3 gold |

### Bonus
- **Scaling livello:** +2% gold per livello
- **Interessi:** +1 gold ogni 10 gold in banca, cap a 50 gold (max +5 gold)
- **PIGGYBANK:** +5 gold per turno in battaglia

### Vendita
- Oggetti: rivendibili al **costo originale**
- Rot: rivendibili (perso con tutti i suoi upgrade)
- Mosse e Drugs: **non rivendibili**

---

## DIFFICOLTA AI

- AI guadagna **+0.5% danno** per livello
- AI riceve **-0.5% danno** per livello
- AI diventa più smart strategicamente man mano
- Nessun bonus da negozio per i Rot nemici

---

## NEGOZIO

Si apre dopo ogni vittoria. 4 sezioni indipendenti con tasto reroll indipendente.

### Costo reroll
- 1 gold il primo reroll di quella sezione
- +1 per ogni reroll successivo della stessa sezione
- Si resetta ad ogni nuovo negozio

### Sezioni
| Sezione | Contenuto | Quantità |
|---|---|---|
| ROT | 1 Rot casuale tra i 16 (doppioni ammessi) | 1 |
| OGGETTI | Oggetti casuali | 2 |
| DRUGS | Drug casuale | 1 |
| MOSSE | Mosse casuali | 2 |

### Prezzi suggeriti
| Categoria | Comune | Rara | Atomica | Apocalittica |
|---|---|---|---|---|
| Rot | 3 gold | — | — | — |
| Oggetti | 2 gold | 4 gold | 7 gold | 15 gold |
| Drugs | 1 gold | 3 gold | 6 gold | — |
| Mosse | 2 gold | 4 gold | 7 gold | — |

### Regole negozio Rot
- Se hai già 3 Rot devi prima venderne uno per fare spazio
- Il Rot acquistato è al livello corrente della squadra
- Rot venduto = perso con tutti i suoi upgrade

### Mosse per Rot
- Ogni Rot può avere max **4 mosse**
- Slot 1: mossa unica del Rot (non sostituibile)
- Slot 2-4: mosse di tipo (sbloccate per livello) o mosse acquistate al negozio
- Le mosse negli slot 2-4 sono intercambiabili liberamente

---

## BOSS FIGHT — BEPPE SALA

Ogni 50 livelli (50, 100, 150, 200...) appare una battaglia boss invece della normale battaglia con 3 ROT nemici — BEPPE SALA li sostituisce completamente.

### BEPPE SALA
- Sostituisce completamente i 3 ROT nemici — occupa tutto lo spazio della squadra nemica
- Gigante — barra HP molto più grande del solito, cambia colore dal verde al rosso
- Stats base = 5 ROT normali sommati, tutte le stats uguali tra loro
- **Formula crescita esponenziale:** stats = stats_base × (livello_boss / 50)^1.5
  - Livello 50: x1 | Livello 100: x2.8 | Livello 150: x5.2 | Livello 200: x8
- Attacca una volta per turno con mossa casuale tra:
  - SALONE DEL MOBILE — fisico, 25 danni a tutti i ROT alleati
  - AREA C — speciale, 25 danni a tutti i ROT alleati
  - RELAX — recupera il 35% degli HP massimi
  - GENTRIFICARE — +1 stadio ATK SP.ATK DEF SP.DEF SPD
- Prima della battaglia appare schermata avviso con countdown 3 secondi

## SISTEMA DI BATTAGLIA

### Struttura turno
1. **Fase pianificazione:** selezioni mossa + bersaglio per tutti i tuoi Rot
2. **Fase esecuzione:** tutti gli attacchi partono in ordine di Speed
3. Parità di Speed → attacca prima il giocatore
4. Se un Rot va KO prima di usare la sua mossa pianificata → mossa annullata
5. **Reindirizzamento automatico:** se il bersaglio di un attacco offensivo viene eliminato prima che il ROT attaccante agisca, l'attacco viene reindirizzato al prossimo ROT nemico vivo (priorità a destra del bersaglio originale). Il log mostra 'Bersaglio eliminato — attacco reindirizzato a [nome ROT]'

### Selezione mosse (UI)
- Freccia sopra il Rot alleato selezionato (frecce o mouse)
- Click → si apre finestra mosse
- Selezionata la mossa → freccia appare sui Rot nemici (attacco) o alleati (buff/cura)
- Mosse ad area → parentesi intorno al gruppo + freccia
- Barra sequenza attacchi in alto, basata sulla Velocità
- Indicatore efficacia sulla freccia di selezione (super efficace / neutro / resistente)

### UI Battaglia
- Barre HP sopra la testa di ogni Rot (nessun numero, solo barra colorata)
- Stat nemici nascoste (solo barra HP visibile)
- In alto a destra: pannello buff permanenti AI che si accumulano per livello

---

## BILANCIAMENTO EARLY GAME

### Buff danno iniziale
- Al turno 1 di ogni battaglia il giocatore ha +50% danno su tutti gli attacchi
- Il bonus scala di -1% per ogni turno fino ad arrivare a 0% al turno 50
- Dal turno 50 in poi nessun bonus
- Si resetta ad ogni nuova battaglia

### Buff difensivo iniziale
- Al turno 1 di ogni battaglia il giocatore riceve il 25% di danno in meno
- Il bonus scala di -0.5% per ogni turno fino ad arrivare a 0% al turno 50
- Dal turno 50 in poi nessun bonus
- Si resetta ad ogni nuova battaglia

### Fusione ROT — Sistema CASAFORTE
- Nella finestra gestione ROT, sotto la sezione marsupio, appare un pulsante CASAFORTE con icona casetta
- Cliccando si apre una grande finestra in sovraimpressione con griglia 4x4 (come il marsupio) dove si depositano i ROT extra acquistati nel negozio, con sezione VENDI tratteggiata in basso
- Se si possiedono 3 ROT dello stesso tipo (in qualsiasi combinazione tra squadra e casaforte), i loro token lampeggiano di rosso come per gli oggetti
- Click destro su un token fondibile apre finestra: "VUOI FONDERE [nome ROT]?" con opzioni VAIIII e NO
- Animazione di fusione → il ROT risultante è uguale ma con scritta EVO 1 accanto al nome nel token
- Fusione di 3 ROT EVO 1 → ROT EVO 2 con sprite aggiornato dalla cartella spritesheet/evo/
- Fusione di 3 ROT EVO 2 → ROT EVO 3 (sprite rimane EVO 2, solo stats aumentate)
- Massimo EVO 3
- La finestra CASAFORTE si chiude cliccando fuori

**Formula stats fusione (due fasi):**
1. Media delle stats dei 3 ROT da fondere includendo l'effetto OVERDOSE già applicato come modifica permanente fissa (l'OVERDOSE è già incorporata nelle stats del ROT che l'ha assunta, si spalma automaticamente nella media) × 1.5
2. Sopra la media evoluta si sommano tutti i bonus delle altre drugs assunte dai 3 ROT fusi, esclusa OVERDOSE già incorporata nella media
- OVERDOSE può essere assunta da qualsiasi ROT a qualsiasi livello EVO senza restrizioni — se un ROT EVO assume OVERDOSE, modifica permanentemente le sue stats e questo si riflette nella media alla fusione successiva
- Il ROT evoluto mantiene un tracking completo di tutte le drugs assunte dai ROT che hanno partecipato alla fusione, inclusa OVERDOSE — nella sezione drugs del ROT evoluto vengono mostrate tutte le drugs cumulative di tutti i ROT fusi con il conteggio corretto per ciascuna drug, incluso il numero totale di OVERDOSE assunte dai ROT componenti e da eventuali OVERDOSE assunte direttamente dal ROT evoluto stesso. L'effetto di OVERDOSE rimane sempre applicato solo sul singolo ROT al momento dell'assunzione, mai post-fusione, ma il tracking del numero totale rimane visibile nella scheda del ROT evoluto
- EVO 1: media × 1.5 + drugs sommate (esclusa OVERDOSE) | EVO 2: media delle 3 EVO 1 × 1.5 + drugs sommate | EVO 3: media delle 3 EVO 2 × 1.5 + drugs sommate

### Oggetti per ROT
- Ogni ROT può equipaggiare massimo **2 oggetti** fino al livello 49
- Dal livello 50: +1 slot oggetto ogni 50 livelli
  - Livello 50: 3 oggetti
  - Livello 100: 4 oggetti
  - Livello 150: 5 oggetti
  - Livello 200: 6 oggetti

### Talenti
- Si sbloccano al livello 50, aumentano di potenza ogni 50 livelli
- Ogni ROT ha il proprio talento unico (le passive già definite)

### Fusione oggetti
- Si attiva automaticamente quando si possiedono 3 oggetti con lo stesso nome e stesso livello (in qualsiasi combinazione tra marsupio e slot equipaggiati sui ROT)
- I 3 token lampeggiano con bordo rosso evidente quando la fusione è disponibile
- Tasto destro su un token attivo apre conferma "Vuoi fondere 3 [nome oggetto] per creare un oggetto più potente?" con SI/NO
- Animazione di fusione stile Pokémon, poi appare il nuovo oggetto fuso con nome, numero di fusione e descrizione aggiornata
- Livelli di fusione: da livello 1 (base) fino a livello 5 — ogni fusione raddoppia l'effetto base dell'oggetto rispetto al livello precedente
- Esempio: LENTINE (riduce danno speciale 20%) → LENTINE 2 (40%) → LENTINE 3 (80%) → LENTINE 4 → LENTINE 5
- Gli oggetti fusi non possono essere scomposti
- Vendendo un oggetto fuso si ottiene il gold equivalente alla somma di tutti i sotto-oggetti usati nella fusione (es. LENTINE 3 fatto da 9 LENTINE base da 2g ciascuna = 18g alla vendita)
- Ogni oggetto ha un'icona dedicata mostrata nella sezione acquisto oggetti e nei token in tutte le finestre invece del nome testuale
- Colore del token per livello fusione: livello 1 giallo, livello 2 arancione, livello 3 rosso bordeaux, livello 4 blu elettrico, livello 5 viola shocking
- Hover sul token fa lampeggiare e apre finestra info con nome, livello e descrizione aggiornata in base al livello

## SCALING LIVELLO ROT

- Tutte le stat aumentano di **+1 per livello**
- Le mosse di tipo si sbloccano ai livelli **10, 50, 100**
- La passiva si sblocca al **livello 50** e scala ogni 50 livelli
- **Difficoltà nemici (dal livello 51):** i ROT nemici ricevono un bonus aggiuntivo di +1% a tutte le stats totali per ogni livello oltre il 50, cumulativo e permanente per tutta la run. Il moltiplicatore attuale è mostrato in piccolo nella barra superiore di battaglia, allineato a destra sotto il pulsante impostazioni, sulla stessa riga della velocità

### Progressione nemici per fascia di livello
| Fascia | EVO ROT nemici | Mosse equipaggiate | Oggetti equipaggiati | Slot oggetti |
|---|---|---|---|---|
| Livello 1-49 | Nessuna EVO (base) | Mossa nativa fissa + mosse Liv 1 casuali tra quelle acquistabili nel negozio (ATTACCO sostituibile) | Liv 1 casuali | 2 slot |
| Livello 50-99 | EVO 1 (sprite base) | Mossa nativa fissa + mosse Liv 2 casuali tra quelle acquistabili nel negozio | Liv 2 casuali | 3 slot |
| Livello 100-149 | EVO 2 (sprite aggiornato da spritesheet/evo/) | Mossa nativa fissa + mosse Liv 3 casuali tra quelle acquistabili nel negozio | Liv 3 casuali | 4 slot |
| Livello 150+ | EVO 3 (sprite EVO 2 invariato, solo stats aumentate) | Mossa nativa fissa + mosse Liv 4 casuali tra quelle acquistabili nel negozio | Liv 4 casuali | 5 slot |

---

## ASSET RICHIESTI

- 16 spritesheet PNG animati (uno per Rot)
- Formato spritesheet: griglia di frame, 5 colonne
- Rot Shiny: versione con saturazione aumentata + leggermente più grande
- Font e UI da definire con il developer
