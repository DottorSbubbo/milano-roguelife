# MILANO ROGUELIFE — Game Design Document

## Panoramica
Roguelike a turni con meccanica di cattura e potenziamento di creature chiamate **ROT**. Run infinite con difficoltà crescente. Nessuna fine — si va avanti finché l'AI non diventa troppo forte.

---

## I ROT (Creature)

Le creature si chiamano **ROT** (non Pokémon).

### Rot Shiny
- Probabilità **0.01%** di apparire (come starter o nel negozio)
- Aspetto: saturazione aumentata + leggermente più grande in battaglia
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
**Talento (liv 50):** AIRDROP — CRYPTOBISMOL inizia ogni battaglia con 2 buff casuali già attivi. Scaling: +2 buff casuali ogni 50 livelli (liv 50: 2 buff, liv 100: 4 buff, liv 150: 6 buff, liv 200: 8 buff...) infinito oltre il liv 200

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
**Talento (liv 50):** SOTTOVUOTO — FERITE viene applicato sempre con qualsiasi fonte di danno e con qualsiasi mossa usata da BRASATO. Scaling: ogni stack FERITE infligge +10% danno aggiuntivo extra ogni 50 livelli (liv 50: +10%, liv 100: +20%, liv 150: +30%, liv 200: +40%...) infinito oltre il liv 200

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
**Mossa unica:** ALCOLISMO — Utility, ARTMIR ottiene uno scudo pari al 15% dei propri HP totali. Per 3 turni, se un attacco colpirebbe un ROT alleato, viene reindirizzato su ARTMIR invece
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

## MOSSE DI TIPO (sbloccate ai livelli 10/50/100, acquistabili al negozio)

### MOG
- **COLPO SIGMA** — Fisico, 40 danni
- **NO NUT** — Speciale, 40 danni
- **SHAKER PROTEICO** — Utility: nel turno di utilizzo danno ricevuto -50% + applica AVVELENATO a chi attacca. Non usabile consecutivamente

### CRYPTO
- **BITCOINK** — Fisico, 40 danni
- **MEME COIN** — Speciale, 40 danni
- **POLYMARKET** — Utility: nel turno di utilizzo danno ricevuto -50% + applica TASCHE BUCATE a chi attacca. Non usabile consecutivamente

### NORMIE
- **FOTO DI GRUPPO** — Fisico, 40 danni
- **CELEBRITY GOSSIP** — Speciale, 40 danni
- **NPC ROUTINE** — Utility: nel turno di utilizzo danno ricevuto -50% + applica COLLASSO a chi attacca. Non usabile consecutivamente

### VAPE
- **TOSSE CRONICA** — Fisico, 40 danni
- **SVAPATA** — Speciale, 40 danni
- **MISCELATORE** — Utility: nel turno di utilizzo danno ricevuto -50% + applica STRAFATTO a chi attacca. Non usabile consecutivamente

### SCHIZO
- **2 DIMENSIONI** — Fisico, 2 colpi da 20 danni
- **4CHAN THEORY** — Speciale, 2 colpi da 20 danni
- **POTERI FORTI** — Utility: tutta la squadra alleata ottiene probabilità critico al 75% per tutta la battaglia. Non usabile consecutivamente

### TROLL
- **TESCHIO** — Fisico, 40 danni
- **GHIGNO MALEFICO** — Speciale, 40 danni
- **BAIT SUPREMO** — Utility: nel turno di utilizzo danno ricevuto -50% + applica BURNOUT a chi attacca. Non usabile consecutivamente

### PSYCHO
- **CORPORATE** — Fisico, 30 danni, +10 per ogni uso consecutivo (si resetta cambiando mossa)
- **HR** — Speciale, 30 danni, +10 per ogni uso consecutivo (si resetta cambiando mossa)
- **DOGE** — Utility: nel turno di utilizzo danno ricevuto -50% + applica BRUCIATO a chi attacca. Non usabile consecutivamente

### BASED
- **CHA CHA CHAD** — Fisico, 20 danni, colpisce da 1 a 4 volte (probabilità colpi aggiuntivi proporzionale alle stat)
- **CANNONE SWAG** — Speciale, 20 danni, colpisce da 1 a 4 volte. Stessa meccanica di CHA CHA CHAD ma usa SP.ATK invece di ATK per calcolare la probabilità
- **SALSA BASE** — Utility: per 3 turni ogni colpo ha 10% di probabilità di stunnare il bersaglio (salta il turno). Non usabile consecutivamente

---

## STATUS

| Status | Effetto | Durata | Stack | Note |
|---|---|---|---|---|
| **AVVELENATO** | -10% HP per turno | Permanente | No | Non staccabile |
| **STRAFATTO** | 50% chance di mancare | 3 turni | No | Non staccabile |
| **TASCHE BUCATE** | -5 gold per turno | Intero combattimento | No | Gold min 0 |
| **BRUCIATO** | -5 HP fissi per turno | Permanente | Sì, max 3 | 3 stack = -15 HP per turno |
| **BURNOUT** | No stessa mossa 2x + doppio PP consumo | 5 turni | No | |
| **COLLASSO** | Salta turno, 50% sveglia per turno | Variabile | No | |
| **FERITE** | +10% danno subito per stack | Permanente | Sì, max 5 | Ogni attacco di Brasato aggiunge 1 stack |

### PP
- Tutte le mosse hanno **10 PP** (tranne ATTACCO base che è infinito)
- PP esauriti = mossa non utilizzabile
- Tutti PP esauriti = Rot non può fare nulla quel turno

### Probabilità status
- Default: **30%** di applicazione salvo eccezioni specifiche

---

## MOSSE GENERICHE NEGOZIO

### COMUNI (70%)
| Mossa | Effetto |
|---|---|
| BIRRETTA | +2 stadi Attacco personale |
| CAFFE | +2 stadi Velocità personale |
| ACTIMEL | +2 stadi Difesa personale |
| UNO BRAVO | +2 stadi Difesa Speciale personale |
| PIPPARE | +2 stadi Attacco Speciale personale |
| MAKE UP | Scudo 25% HP massimi personali |
| URCA | -50% danno dal prossimo attacco ricevuto |
| SCHEDINA | Guadagni 10% del gold posseduto |
| LAMPIONE | Per 3 turni il team è immune a stun e abbassamento stat |
| TERME | Elimina ogni malus da un Rot |
| OFFRO IO | Il team recupera 15% HP massimi |
| APRI LE FINESTRE | Elimina tutti gli status che modificano le statistiche |

### RARE (15%)
| Mossa | Effetto |
|---|---|
| **SBERLATE** | Fisico, 50 danni a tutti i ROT nemici contemporaneamente |
| **BORDELLO** | Speciale, 50 danni a tutti i ROT nemici contemporaneamente |

### RARE (15%)
| Mossa | Effetto |
|---|---|
| ABBRACCIO | Scudo 15% HP massimi a tutto il team |
| TOH | Trasferisce tutti i malus di un Rot alleato a un Rot nemico |
| CHINOTTO | Un Rot alleato selezionato recupera 50% HP |
| PROVACI | +15% danno subito dal prossimo attacco, restituisce 100% del danno all'attaccante |
| FRULLATO DETOX | +2 stadi Difesa e Difesa Speciale a tutto il team |
| SHOTTINI | +2 stadi Attacco e Attacco Speciale a tutto il team |
| REDBULL | +2 stadi Velocità a tutto il team |

### ATOMICHE (5%)
| Mossa | Effetto |
|---|---|
| BESTEMMIA | Protezione completa da qualsiasi attacco per 1 turno. Non usabile consecutivamente |
| LANDLORDARE | Per 5 turni il team recupera 10% HP massimi a fine turno |

### MOSSE TIPO (10% — le 24 mosse di tipo sopra elencate)

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
- **Difficoltà nemici (dal livello 51):** i ROT nemici ricevono un bonus aggiuntivo di +1% a tutte le stats totali per ogni livello oltre il 50, cumulativo e permanente per tutta la run (es. al livello 60 i nemici hanno +10% stats rispetto al valore base previsto per quel livello). Il moltiplicatore attuale è mostrato in piccolo nella barra superiore di battaglia, allineato a destra sotto il pulsante impostazioni, sulla stessa riga della velocità

---

## ASSET RICHIESTI

- 16 spritesheet PNG animati (uno per Rot)
- Formato spritesheet: griglia di frame, 5 colonne
- Rot Shiny: versione con saturazione aumentata + leggermente più grande
- Font e UI da definire con il developer
