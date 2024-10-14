+++
title = 'Chiavi e indirizzi'
author = 'me'
date = 2024-10-13
weight = 4
draft = true
+++

> [!important] Brief:
> Questa sezione ti aiuterà a capire cosa sono le chiavi private, le chiavi pubbliche, gli indirizzi e che relazioni ci sono tra loro.

> [!TIP]+ Con parole semplici
> ##### Immagina una cassetta delle lettere
> Per capire questi concetti, immagina di avere una cassetta delle lettere, in cui è presente una fessura di ingresso (chiave pubblica) ed una serratura (chiave privata).
> Ecco come funziona:
> - **Chiave pubblica**: è la chiave che puoi dare a chiunque, di modo che chiunque possa inserire dei bitocin nella tua cassetta, ma non può aprirla.
> - **Chiave privata**: è la chiave segreta che solo tu possiedi. Serve per aprire la cassetta e prendere i tuoi bitcoin. Se qualcun altro avesse questa chiave, potrebbe rubare tutto!
> ##### Come si creano le chiavi?
> - La **chiave privata** viene generata per prima. È come se tu creassi una password segreta super lunga e complessa. Questa chiave privata è unica e quasi impossibile da indovinare; è così importante che devi custodirla con estrema attenzione.
> - La **chiave pubblica** è creata a partire dalla chiave privata, grazie a una specie di "trucchetto matematico". Anche se chiunque può vedere la tua chiave pubblica, non può risalire alla tua chiave privata.
> ##### E gli indirizzi?
> Ora, immagina che qualcuno spii quante persone mettono qualcosa nella tua cassetta e veda quanti bitcoin ricevi. Per evitarlo, puoi fornire a ciascuno un indirizzo diverso, come se fossero punti di consegna sparsi ovunque, non riconducibili alla tua cassetta principale. Così, tutto ciò che ricevi sarà sempre tuo, ma nessuno potrà spiarti.
> ##### Non perdere la chiave privata!
> Un dettaglio fondamentale: se perdi la tua chiave privata, è come se avessi perso la chiave della tua cassetta per sempre e nessuno potrà più aprirla. Quindi, custodisci la chiave privata con cura, in un luogo sicuro, dove nessun altro può accedervi!

# Chiavi
### Chiave privata

Nella pratica, la chiave privata viene generata da un algoritmo detto _entropia_, che viene alimentato da una sorgente di caos e genera un output mnemonicamente rappresentato da 12 o 24 parole seme, dette _seed phrase_. La conoscenza dalla seed phrase è l'**unico modo** per ricostruire la chiave privata.

La chiave privata è l’elemento crittografico che permette al possessore di bitcoin di spenderlo: viene utilizzata per creare *firme digitali*, dimostrando la proprietà dei fondi in una transazione, che sono necessarie per trasferire i bitcoin.

**La chiave privata deve rimanere segreta in ogni momento**, perché rivelarla a terzi equivale a dare loro il controllo sui bitcoin associati a quella chiave. Deve essere anche protetta da perdite accidentali, perché **se persa non può essere recuperata e i fondi associati ad essa saranno anch’essi persi per sempre**.

È possibile crittografare la chiave privata con una *passphrase* in modo che possa essere archiviata, trasportata o conservata in modo sicuro, anche qualora la chiave fosse esposta.
Una chiave crittografata con passphrase, se decodificata con la stessa passphrase può essere utilizzata in qualsiasi *Wallet*.

La chiave privata sarà costudita all’interno del wallet, il quale fornirà anche una copia di backup (sottoforma di *Seed Phrase*) che sarà l’unico elemento con cui si potrà recuperare l’accesso ai fondi qualora il wallet andasse distrutto o rubato.


### Chiave pubblica

La chiave pubblica viene calcolata a partire dalla chiave privata utilizzando la *crittografia asimmetrica*, che rende irreversibile questa operazione.

Il proprietario della chiave privata può tranquillamente creare una chiave pubblica e condividerla con chiunque, sapendo che nessuno può invertire la funzione e risalire alla chiave privata.

In una transazione, la chiave pubblica del beneficiario identifica univocamente il destinatario, senza tuttavia rivelarne l'anagrafica.


---
#### 5. **Il ruolo della chiave pubblica**
Una volta generata la chiave privata, viene automaticamente creata anche una **chiave pubblica**, attraverso un processo crittografico chiamato **elliptic curve cryptography** (crittografia a curve ellittiche). La chiave pubblica è derivata dalla chiave privata e può essere condivisa con altri, poiché serve per ricevere i fondi. Tuttavia, la chiave privata deve rimanere segreta, poiché è l'unico modo per accedere ai fondi e autorizzare le transazioni.

---

# Indirizzi
### Indirizzi bitcoin

L'indirizzo viene calcolato a partire dalla chiave pubblica utilizzando la [*crittografia asimmetrica*](https://trama81.github.io/bitcoin/1_teoria_base/1_conoscere_bitcoin/3_crittografia/index.html), che rende irreversibile questa operazione.

L’indirizzo bitcoin è quello che appare comunemente in una transazione come il destinatario dei fondi. Nella pratica è però sconsigliato ricevere fondi sempre sullo stesso indirizzo, poichè questo introduce un problema di privacy: poichè la blockchain è pubblica, si può ricercare la chiave pubblica e trovare tutto lo storico delle transazioni, venendo a scoprire il saldo.

La soluzione a questo problema di privacy viene risolto sempre grazie alla crittografia, che a partire dalla stessa coppia di chiavi (privata e pubblica), è in grado di calcolare in modo deterministico una lista di indirizzi anonimi.


---

# Chiavi
### Chiave privata

La chiave privata è una sequenza di numeri e lettere che funge da password segreta per autorizzare le transazioni e quindi per spendere tuoi fondi. Chi possiede la chiave privata ha il pieno controllo sui bitcoin associati a quella chiave.

La generazione di una chiave privata utilizza il concetto di **entropia** (è il grado di casualità in un sistema) per creare una stringa di numeri completamente imprevedibile. Questo è fondamentale per garantire che ogni chiave sia unica e impossibile da indovinare o replicare.

Fonti comuni di entropia includono:
- **Generatori di numeri casuali**: I software di portafogli usano algoritmi avanzati per produrre numeri casuali, combinati e trasformati in una chiave privata.
- **Interazione dell'utente**: In alcuni casi, la casualità può essere aumentata dall'interazione dell'utente, ad esempio muovendo il mouse o lanciando dei dadi, per aggiungere ulteriore imprevedibilità.

La chiave privata di Bitcoin è un numero molto grande, compreso tra 1 e 2²⁵⁶ (circa 10⁷⁷). Questo intervallo garantisce che ci siano un'infinità di possibili chiavi private, rendendo praticamente impossibile generare per errore due chiavi uguali.

Per semplificare l'uso di queste chiavi, vengono spesso rappresentate in **formato esadecimale** (utilizzando cifre da 0 a 9 e lettere da A a F). Un esempio di chiave privata in formato esadecimale potrebbe essere:
```
5Kb8kLf9zgWQnogidDA76MzPL6TsZZY36hWXMssSzNydYXYB9KF
```

Poiché ricordare una stringa lunga di caratteri alfanumerici è difficile, la chiave privata viene convertita in una sequenza di 12 o 24 parole semplici da ricordare, chiamata **seed phrase** o frase seme. Questa frase viene generata attraverso lo standardadmin
 [**BIP-39**](https://github.com/bitcoin/bips/blob/master/bip-0039/english.txt), che assegna una lista di parole predefinite a diversi segmenti della chiave privata. Ad esempio, una seed phrase potrebbe essere:
```
arena soldier album virus drift charge tree unveil follow poet lucky fashion
```

Questa serie di parole è un modo più umano e sicuro di gestire la chiave privata, poiché è più facile da memorizzare o annotare rispetto alla sequenza esadecimale. La frase seme può essere usata per ricostruire la chiave privata in qualsiasi portafoglio compatibile.

Alcuni portafogli offrono un ulteriore livello di sicurezza, consentendo di proteggere la frase seme con una **passphrase**. Questo significa che, anche se qualcuno scoprisse la tua seed phrase, senza la passphrase non potrebbe accedere ai tuoi fondi. La passphrase funziona come un'ulteriore parola segreta e fornisce un livello di protezione in più.







### Come funziona la firma digitale?

Quando si effettua una transazione in Bitcoin, entra in gioco la **firma digitale**, che è un meccanismo crittografico utilizzato per garantire che il proprietario della chiave privata sia effettivamente colui che sta autorizzando la transazione. La firma digitale è una delle parti più importanti del sistema Bitcoin, perché consente di nascondere la chiave privata senza comprometterne la funzione.

Ecco come funziona il processo:
1. **Creazione della firma**: Quando invii bitcoin, il software del portafoglio utilizza la tua chiave privata per creare una firma digitale. Questa firma è un insieme di dati che conferma che tu possiedi la chiave privata senza mai rivelarla.
2. **Verifica della firma**: Una volta creata, la firma digitale viene verificata da altri nodi della rete Bitcoin utilizzando la tua **chiave pubblica**. Questi nodi possono confermare che la firma è stata creata da chi possiede la chiave privata associata alla chiave pubblica, senza che la chiave privata stessa venga esposta. In questo modo, la rete garantisce che solo il proprietario effettivo dei bitcoin possa spenderli, mantenendo al sicuro la chiave privata.
   
La firma digitale protegge quindi l'identità del mittente e garantisce che la transazione sia legittima, senza rivelare direttamente la chiave privata. Questo è uno degli aspetti fondamentali che permette a Bitcoin di funzionare in modo sicuro e decentralizzato.

### Perché la chiave privata è fondamentale?

La chiave privata è ciò che ti consente di spendere i tuoi bitcoin. Ogni volta che invii bitcoin a qualcun altro, la chiave privata viene utilizzata per creare la firma digitale, confermando che sei il legittimo proprietario dei fondi. Questo processo, pur essendo invisibile all'utente, è cruciale per mantenere la sicurezza della rete Bitcoin.

**La segretezza della chiave privata è di vitale importanza.** Se qualcuno entra in possesso della tua chiave, può accedere e trasferire i tuoi fondi senza il tuo permesso. Non esistono meccanismi per recuperare i bitcoin rubati, quindi è essenziale conservare la chiave privata in modo sicuro.

### Cosa succede se perdi la chiave privata?

Se perdi la tua chiave privata, perdi anche l'accesso ai tuoi bitcoin. Non c'è un sistema centralizzato che possa ripristinarla, ed è per questo che la frase seme diventa fondamentale. La _seed phrase_ è l'unico metodo per recuperare la tua chiave privata se il tuo portafoglio viene smarrito o danneggiato. È importante conservare questa frase in un luogo sicuro, perché chiunque ne venga a conoscenza può ricostruire la tua chiave privata e prendere possesso dei tuoi fondi.

### Come proteggere la chiave privata

Esistono diversi metodi per proteggere la tua chiave privata. Alcuni portafogli ti permettono di crittografarla con una _passphrase_ aggiuntiva, creando un ulteriore strato di sicurezza. In questo modo, anche se la tua chiave venisse esposta, sarebbe inutilizzabile senza la passphrase corretta.

Inoltre, molti utenti scelgono di utilizzare hardware wallet, dispositivi fisici progettati appositamente per conservare le chiavi private in modo sicuro, offline e al riparo da attacchi informatici.

### Conclusione

La chiave privata è il cuore del sistema Bitcoin: senza di essa, non puoi accedere ai tuoi fondi o autorizzare transazioni. Proteggerla in modo sicuro è fondamentale per mantenere il controllo dei tuoi bitcoin. Assicurati di fare copie della tua _seed phrase_ e di conservarla in luoghi sicuri, perché la sicurezza delle tue criptovalute dipende interamente da quanto bene riesci a proteggere la tua chiave privata.

---

Questa versione integra la spiegazione sul funzionamento della firma digitale, chiarendo come la chiave privata rimane nascosta ma allo stesso tempo garantisce la legittimità delle transazioni.