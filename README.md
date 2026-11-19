# P-8 · Simulatore percussivo semi-modulare

Simulatore da browser di un sintetizzatore percussivo semi-modulare con schema ispirato al Behringer Edge: due oscillatori, filtro ladder, tre inviluppi di decay, sequencer a 8 passi e patch bay. Funziona su computer, tablet e telefono, anche **offline** come app installata.

> Progetto non ufficiale e senza alcun legame con Behringer / Music Tribe. "Behringer" ed "Edge" sono marchi dei rispettivi proprietari e sono citati solo per descrivere lo strumento a cui si ispira il layout. Grafica, codice e suoni sono originali.

## Cosa contiene

- **Due oscillatori** (impulso / triangolo) con FM da OSC 1 a OSC 2 e **hard sync**.
- **Rumore** bianco o rosa, con ingresso audio esterno.
- **Filtro ladder 4 poli**: passa-basso e passa-alto, risonanza fino all'auto-oscillazione (casse in stile 808).
- **Tre inviluppi di decay** (pitch, filtro, VCA) con quantità bipolari.
- **Sequencer a 8 passi** con righe PITCH e VELOCITY, tempo da 10 a 10.000 BPM: sopra circa 2.000 BPM diventa un oscillatore udibile.
- **SEQ PITCH MOD** su OSC 1 e 2, nessuno, o solo OSC 2.
- **Clock** interno, esterno (ADV/CLOCK) o MIDI con divisioni da 1/4 a 1/32T (SCALE).
- **Patch bay** completa con collegamenti interni: un cavo nel jack di ingresso sostituisce o si somma al segnale interno, come indicato nella guida.
- **MIDI** in/out tramite Web MIDI (canale, THRU, note; riceve e invia il clock MIDI con start/stop).
- **Tastiera a schermo** e tastiera del computer (A W S E D F …, Z/X per l'ottava, spazio = PLAY).
- **16 preset** di fabbrica (cassa, rullante, hi-hat, tom, cowbell FM, basso acid, drone e patch d'esempio) e **preset personali**, con esportazione e importazione della **sessione completa**.

## Avvio rapido

1. Apri la pagina e tocca **▶ Accendi** (i browser attivano l'audio solo dopo un tocco).
2. Dal menu **PRESET** scegli un suono e premi **PLAY/STOP**.
3. **TRIGGER** suona lo step corrente senza avanzare; **ADVANCE** passa allo step successivo senza suonare.
4. Per collegare un cavo tocca un'**uscita** e poi un **ingresso**. Toccando un ingresso già collegato il cavo si stacca.
5. Il pulsante **?** apre la guida completa.

## Preset e sessioni

Dal menu **PRESET**:

| Voce | Cosa fa |
|---|---|
| ＋ Salva il suono attuale… | Salva manopole, levette, cavi e la sequenza degli 8 passi con un nome (anche col pulsante SALVA) |
| ★ nome | Richiama un tuo preset |
| ✕ Elimina «nome» | Elimina il preset caricato |
| ⇩ Esporta sessione | Crea `P8-sessione.json` con i tuoi preset e il suono attuale, compresi sequenza, tempo e scala |
| ⇧ Importa sessione o preset | Aggiunge i preset del file e, se confermi, ripristina la sessione |

Tutto viene salvato nel browser. La versione online e quella installata offline hanno memorie separate: per passare da una all'altra usa Esporta e Importa.

## Usarlo offline (iPhone, iPad, Android)

Il simulatore è una PWA: dopo la prima apertura funziona anche senza connessione.

- **iPhone / iPad (Safari)**: apri la pagina, tocca Condividi → **Aggiungi alla schermata Home**.
- **Android (Chrome)**: menu ⋮ → **Installa app**.

Dopo un aggiornamento dei file su GitHub, apri l'app una volta con la connessione attiva per scaricare la nuova versione.

## Compatibilità

- Audio: Chrome, Edge, Firefox, Safari recenti (AudioWorklet, con ripiego automatico se non disponibile).
- MIDI: Chrome ed Edge su computer e Android. Safari e i browser su iPhone/iPad non supportano Web MIDI.

## Note tecniche

Il motore audio gira in un AudioWorklet a frequenza di campionamento piena: oscillatori con anti-aliasing polyBLEP, filtro ladder a ritardo zero (ZDF) con saturazione, inviluppi esponenziali, patch bay elaborata campione per campione.
