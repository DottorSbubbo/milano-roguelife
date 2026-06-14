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
| **MOG** | CRYPTO | VAPE |
| **VAPE** | MOG | TROLL |
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
**Passiva (liv 50):** PALLE SECCHE — AVVELENATO applicabile +1 volta sui nemici. Scaling: +1 applicazione ogni 50 livelli

### ROT #02 — CRYPTOBISMOL
**Tipo:** CRYPTO
**Stat base:** HP 40 / ATK 30 / SP.ATK 80 / DEF 30 / SP.DEF 60 / SPD 60 (TOT 300)
**Mossa unica:** REDDIT — Speciale, 50 danni, 30% di applicare TASCHE BUCATE
**Passiva (liv 50):** HODL — Ogni turno senza essere attaccato guadagna 2 gold. Scaling: +2 gold ogni 50 livelli

### ROT #03 — BIG MAC
**Tipo:** NORMIE
**Stat base:** HP 90 / ATK 40 / SP.ATK 60 / DEF 60 / SP.DEF 40 / SPD 10 (TOT 300)
**Mossa unica:** MENU LARGE — Speciale, 50 danni, 30% di applicare COLLASSO
**Passiva (liv 50):** SUPERSIZED — Ogni volta che subisce un colpo recupera 3% HP. Scaling: +3% ogni 50 livelli

### ROT #04 — CHEESECAKE
**Tipo:** VAPE
**Stat base:** HP 50 / ATK 40 / SP.ATK 60 / DEF 40 / SP.DEF 50 / SPD 60 (TOT 300)
**Mossa unica:** SVAPO DIESEL — Speciale, 50 danni, 30% di applicare STRAFATTO
**Passiva (liv 50):** CLOUD NINE — STRAFATTO dura 1 turno in più sui nemici. Scaling: +1 turno ogni 50 livelli

### ROT #05 — LINO STAGNO
**Tipo:** SCHIZO
**Stat base:** HP 60 / ATK 30 / SP.ATK 50 / DEF 70 / SP.DEF 70 / SPD 20 (TOT 300)
**Mossa unica:** NO VAX — Utility, 0 danni, rimuove tutti gli status negativi dalla squadra + scudo 20% HP max a tutti
**Passiva (liv 50):** SCIE CHIMICHE — NO VAX applica scudo aggiuntivo del 5%. Scaling: +5% ogni 50 livelli

### ROT #06 — TROLLO
**Tipo:** TROLL
**Stat base:** HP 50 / ATK 60 / SP.ATK 50 / DEF 40 / SP.DEF 40 / SPD 60 (TOT 300)
**Mossa unica:** RAGE BAIT — Fisico, 50 danni, 30% di applicare BURNOUT
**Passiva (liv 50):** RATIO — Ogni volta che un nemico manca l'attacco, TROLLO guadagna +1 stadio attacco. Scaling: +1 stadio ogni 50 livelli

### ROT #07 — ELONIO MUSCHIO
**Tipo:** PSYCHO
**Stat base:** HP 50 / ATK 70 / SP.ATK 50 / DEF 40 / SP.DEF 40 / SPD 50 (TOT 300)
**Mossa unica:** FIRED! — Fisico, 50 danni, 30% di applicare BRUCIATO
**Passiva (liv 50):** LAID OFF — BRUCIATO applica 1 stack aggiuntivo automaticamente. Scaling: +1 stack ogni 50 livelli

### ROT #08 — BRASATO
**Tipo:** BASED
**Stat base:** HP 60 / ATK 80 / SP.ATK 30 / DEF 50 / SP.DEF 30 / SPD 50 (TOT 300)
**Mossa unica:** MANNAIA MANNAGGIA — Fisico, 40 danni, applica 1 stack FERITE al bersaglio
**Passiva (liv 50):** FROLLATURA — FERITE applicano +2% danno aggiuntivo per stack (base 10% + 2% per stack ogni 50 livelli). Scaling: +2% ogni 50 livelli

### ROT #09 — MOG MOB
**Tipo:** MOG
**Stat base:** HP 50 / ATK 80 / SP.ATK 30 / DEF 70 / SP.DEF 30 / SPD 40 (TOT 300)
**Mossa unica:** CRIMSON MENTONE — Utility, tutta la squadra: -2 stadi Difesa e Difesa Speciale, +2 stadi Attacco e Attacco Speciale
**Passiva (liv 50):** CHIN CHECK — CRIMSON MENTONE aumenta di +1 stadio aggiuntivo attacco per ogni utilizzo. Scaling: +1 stadio ogni 50 livelli

### ROT #10 — LOGAN FRAUD
**Tipo:** CRYPTO
**Stat base:** HP 40 / ATK 30 / SP.ATK 70 / DEF 30 / SP.DEF 50 / SPD 80 (TOT 300)
**Mossa unica:** RUGPULL — Speciale, 15 danni base +1 danno per ogni Gold in banca
**Passiva (liv 50):** EXIT SCAM — RUGPULL ruba anche il 5% del gold del nemico ad ogni colpo. Scaling: +5% ogni 50 livelli

### ROT #11 — POKE MON
**Tipo:** NORMIE
**Stat base:** HP 70 / ATK 30 / SP.ATK 50 / DEF 50 / SP.DEF 60 / SPD 40 (TOT 300)
**Mossa unica:** TREDICESIMA — Utility, cura tutta la squadra del 25% degli HP massimi di POKE MON
**Passiva (liv 50):** WELFARE — TREDICESIMA cura il 5% in più degli HP massimi. Scaling: +5% ogni 50 livelli

### ROT #12 — SVAPO KINK
**Tipo:** VAPE
**Stat base:** HP 50 / ATK 30 / SP.ATK 70 / DEF 40 / SP.DEF 60 / SPD 50 (TOT 300)
**Mossa unica:** SOFFOCOTTO — Speciale, 30 danni a tutti i nemici contemporaneamente
**Passiva (liv 50):** DIPENDENZA — SOFFOCOTTO colpisce un nemico aggiuntivo casuale. Scaling: +1 bersaglio ogni 50 livelli

### ROT #13 — FRANCO
**Tipo:** SCHIZO
**Stat base:** HP 60 / ATK 40 / SP.ATK 60 / DEF 40 / SP.DEF 40 / SPD 60 (TOT 300)
**Mossa unica:** RICICLAGGIO — Speciale, 30 danni, 50% di applicare uno status casuale
**Passiva (liv 50):** SINISTRO — RICICLAGGIO applica 1 status aggiuntivo casuale. Scaling: +1 status ogni 50 livelli

### ROT #14 — USBATTI
**Tipo:** TROLL
**Stat base:** HP 40 / ATK 80 / SP.ATK 30 / DEF 30 / SP.DEF 30 / SPD 90 (TOT 300)
**Mossa unica:** USB-C — Fisico, 80 danni, recoil 20 danni a USBATTI dopo l'attacco
**Passiva (liv 50):** OVERCLOCK — USB-C non infligge più recoil. Scaling: il recoil diventa +20 danno aggiuntivo al bersaglio ogni 50 livelli

### ROT #15 — SEAO
**Tipo:** PSYCHO
**Stat base:** HP 60 / ATK 50 / SP.ATK 70 / DEF 50 / SP.DEF 50 / SPD 20 (TOT 300)
**Mossa unica:** EVASIONE FISCALE — Fisico, 40 danni a tutti i nemici, 50% di perdere 10% dei propri Gold
**Passiva (liv 50):** TAX HAVEN — EVASIONE FISCALE non ha più la penalità gold. Scaling: recupera invece 5% gold ad ogni uso ogni 50 livelli

### ROT #16 — GIANNI IL PIZZAIOLO SOTTO CASA
**Tipo:** BASED
**Stat base:** HP 70 / ATK 60 / SP.ATK 40 / DEF 60 / SP.DEF 50 / SPD 20 (TOT 300)
**Mossa unica:** CHIACCHIERE DA BAR — Utility, +1 stadio Difesa e Difesa Speciale a tutta la squadra
**Passiva (liv 50):** DOC VERACE — CHIACCHIERE DA BAR aumenta di +1 stadio aggiuntivo. Scaling: +1 stadio ogni 50 livelli

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
| ABBRACCIO | Scudo 15% HP massimi a tutto il team |
| TOH | Trasferisce tutti i malus di un Rot alleato a un Rot nemico |
| CHINOTTO | Un Rot alleato selezionato recupera 50% HP |
| PROVACI | +15% danno subito dal prossimo attacco, restituisce 100% del danno all'attaccante |
| FRULLATO DETOX | +1 stadio Difesa e Difesa Speciale a tutto il team |
| SHOTTINI | +1 stadio Attacco e Attacco Speciale a tutto il team |
| REDBULL | +1 stadio Velocità a tutto il team |

### ATOMICHE (5%)
| Mossa | Effetto |
|---|---|
| BESTEMMIA | Protezione completa da qualsiasi attacco per 1 turno. Non usabile consecutivamente |
| LANDLORDARE | Per 5 turni il team recupera 10% HP massimi a fine turno |
| CENTRO SOCIALE | Per 3 turni ogni buff ricevuto viene copiato su un alleato casuale |
| CORONAVIRUS | Per 3 turni ogni status negativo applicato a un nemico viene copiato su un altro nemico casuale |

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

### COMUNI (80%)
| Oggetto | Effetto |
|---|---|
| TUTINA | Riduce danno fisico ricevuto del 5% |
| OCCHIALI DA SOLE | Riduce danno speciale ricevuto del 5% |
| MANUBRIETTO | +5% danno fisico inflitto |
| LENTINE | +5% danno speciale inflitto |
| SCARPE DA GINNASTICA | Il Rot attacca sempre per primo, 1 volta per battaglia |
| CEROTTO | Se scende sotto 25% HP recupera 20% HP, una volta per battaglia |
| PORTAFORTUNA | +5% probabilità che gli status applicati vadano a segno |
| ASSICURAZIONE | Se il Rot muore non viene perso, una volta per run |
| PIGGYBANK | +5 gold per ogni turno in battaglia |
| PELLE DI ROSPO | Immunità a tutti gli status negativi |
| ZOCCOLI DI LEGNO | Il Rot attacca sempre per ultimo, indipendentemente dalla velocità |

### RARE (15%)
| Oggetto | Effetto |
|---|---|
| GIUBBOTTO ANTIPROIETTILE | Riduce danno fisico ricevuto del 15% |
| LENTI A CONTATTO | Riduce danno speciale ricevuto del 15% |
| BILANCIERE | +15% danno fisico inflitto |
| TELESCOPIO | +15% danno speciale inflitto |
| SPECCHIO | 20% di riflettere uno status negativo all'attaccante |
| SPINACIO | Restituisce 15% del danno subito ad ogni attacco |

### ATOMICHE (4%)
| Oggetto | Effetto |
|---|---|
| TUTA BULLETPROOF | Riduce tutto il danno ricevuto del 20% |
| FENICE | Se il Rot va KO si riprende una volta con 50% HP |
| CARTA DI CREDITO | Raddoppia il gold guadagnato per tutta la run |
| AMULETO OSCURO | Ogni attacco ha 15% di applicare uno status casuale al nemico |
| AVANZI | Ogni turno il Rot recupera 5% dei propri HP massimi |

### APOCALITTICA (1%)
| Oggetto | Effetto |
|---|---|
| SBUBBO | Il Rot attacca due volte consecutivamente per ogni attacco |

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
- Ogni ROT può equipaggiare massimo **2 oggetti** contemporaneamente

## SCALING LIVELLO ROT

- Tutte le stat aumentano di **+1 per livello**
- Le mosse di tipo si sbloccano ai livelli **10, 50, 100**
- La passiva si sblocca al **livello 50** e scala ogni 50 livelli

---

## ASSET RICHIESTI

- 16 spritesheet PNG animati (uno per Rot)
- Formato spritesheet: griglia di frame, 5 colonne
- Rot Shiny: versione con saturazione aumentata + leggermente più grande
- Font e UI da definire con il developer
