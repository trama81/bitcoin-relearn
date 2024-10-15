+++
title = 'Chiavi e indirizzi'
author = 'me'
date = 2024-10-15
weight = 4
draft = false
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

La chiave privata è una sequenza di numeri e lettere che funge da password segreta per autorizzare le transazioni e quindi per spendere tuoi fondi. Chi possiede la chiave privata ha il pieno controllo sui bitcoin associati a quella chiave.

La generazione di una chiave privata utilizza il concetto di **entropia** (è il grado di casualità in un sistema) per creare una stringa di numeri completamente imprevedibile. Questo è fondamentale per garantire che ogni chiave sia unica e impossibile da indovinare o replicare.

```mermaid { align="center" zoom="false" }
---
title:
---
graph LR;
  A(Entropia)  --> | n = 1158 * 10⁷⁷ | B(Algoritmo SHA256)
  B(Algoritmo SHA256) --> |n = 256 bit| C(Chiave privata)
```

Fonti comuni di entropia includono:
- **Generatori di numeri casuali**: I software di portafogli usano algoritmi avanzati per produrre numeri casuali, combinati e trasformati in una chiave privata.
- **Interazione dell'utente**: In alcuni casi, la casualità può essere aumentata dall'interazione dell'utente, ad esempio muovendo il mouse o lanciando dei dadi, per aggiungere ulteriore imprevedibilità.

La chiave privata di Bitcoin è un numero molto grande, compreso tra 1 e 2²⁵⁶ (circa 10⁷⁷). Questo intervallo garantisce che ci siano un'infinità di possibili chiavi private, rendendo praticamente impossibile generare per errore due chiavi uguali.

Per semplificare l'uso di queste chiavi, vengono spesso rappresentate in **formato esadecimale** (utilizzando cifre da 0 a 9 e lettere da A a F). Un esempio di chiave privata in formato esadecimale potrebbe essere:

```
5Kb8kLf9zgWQnogidDA76MzPL6TsZZY36hWXMssSzNydYXYB9KF
```

Poiché ricordare una stringa lunga di caratteri alfanumerici è difficile, la chiave privata viene convertita in una sequenza di 12 o 24 parole semplici da ricordare, chiamata **seed phrase** o frase seme. Questa frase viene generata attraverso lo standard [**BIP-39**](https://github.com/bitcoin/bips/blob/master/bip-0039/english.txt), che assegna una lista di parole predefinite a diversi segmenti della chiave privata. Ad esempio, una seed phrase potrebbe essere:
 
```
arena soldier album virus drift charge tree unveil follow poet lucky fashion
```

Questa serie di parole è un modo più umano e sicuro di gestire la chiave privata, poiché è più facile da memorizzare o annotare rispetto alla sequenza esadecimale. La frase seme può essere usata per ricostruire la chiave privata in qualsiasi portafoglio compatibile.

Alcuni portafogli offrono un ulteriore livello di sicurezza, consentendo di proteggere la frase seme con una **passphrase** aggiuntiva, creando un ulteriore strato di sicurezza. In questo modo, anche se la tua chiave venisse esposta, sarebbe inutilizzabile senza la passphrase corretta.

La chiave privata è il cuore del sistema Bitcoin, poiché consente l'accesso ai fondi e l'autorizzazione delle transazioni. Se qualcuno dovesse ottenerla, potrebbe trasferire i tuoi bitcoin senza il tuo consenso, e poiché non esistono meccanismi per recuperare i fondi rubati, la sicurezza dei tuoi bitcoin dipende interamente da quanto bene riesci a proteggere la tua chiave privata. Se la perdi, perdi anche l'accesso ai tuoi bitcoin, poiché non esiste un sistema centralizzato che possa ripristinarla. L'unico modo per recuperarla è tramite la _seed phrase_.

### Chiave pubblica

La **chiave pubblica** è un elemento essenziale per garantire la sicurezza e la trasparenza delle transazioni. Si tratta di una stringa alfanumerica generata dalla chiave privata, che consente di ricevere bitcoin e verificare le transazioni senza compromettere la sicurezza dei fondi.

Svolge due ruoli principali:
1) **Ricezione di fondi**: quando qualcuno vuole inviarti bitcoin, entra in gioco la tua chiave pubblica, che viene trasformata in un **indirizzo Bitcoin** da fornire al mittente per semplificare e rendere più sicuro l'invio dei fondi.
    
2) **Verifica delle transazioni**: permette di autenticare l'origine dei fondi e di garantire che solo il legittimo proprietario della chiave privata possa autorizzare il movimento dei bitcoin.

La chiave pubblica viene calcolata a partire dalla chiave privata utilizzando la *crittografia asimmetrica* (moltiplicazione delle curve ellittiche), che rende irreversibile questa operazione.

```mermaid { align="center" zoom="false" }
---
title:
---
graph LR;
  A(Chiave privata)   --> | n = 256 bit | B(Elliptic Curve Multiplication)
  B(Elliptic curve multiplication) --> | K = k * G | C(Chiave pubblica) 
```
dove:
: k = chiave privata
: K = chiave pubblica risultante
: G = punto di generazione della curva ellittica

La chiave pubblica così generata identifica univocamente il beneficiario senza rivelarne l'anagrafica e può essere condivisa con chiunque, sapendo che nessuno può invertire la funzione e risalire alla chiave privata. Se però qualcuno riuscisse a collegare la tua chiave pubblica alla tua identità reale, potrebbe monitorare sulla blockchain tutte le tue transazioni e risalire al tuo saldo associato a quella chiave pubblica, violando la tua privacy. Per questo motivo, è doveroso adottare pratiche di sicurezza aggiuntive, come creare nuovi indirizzi bitcoin per ogni transazione.


---

# Indirizzi
### Indirizzi bitcoin

Gli **indirizzi Bitcoin** sono un elemento cruciale per inviare e ricevere fondi nella rete Bitcoin. Agiscono come un numero di conto, ma in modo decentralizzato e sicuro, permettendo di ricevere bitcoin senza rivelare informazioni sensibili. Esistono diversi tipi di indirizzi Bitcoin, ciascuno con caratteristiche specifiche che si sono evolute nel tempo per migliorare la sicurezza, l’efficienza e l’usabilità della rete. Utilizzare correttamente gli indirizzi e adottare le misure di sicurezza appropriate è essenziale per proteggere i tuoi fondi e la tua privacy.

Gli indirizzi Bitcoin vengono generati dalla chiave pubblica, attraverso una funzione di hashing crittografica.

```mermaid { align="center" zoom="false" }
---
title:
---
graph LR;
  A(Chiave pubblica)    --> B(SHA256 & RIPEMD160)
  B(SHA256 & RIPEMD160) --> |K = 160 bit| C(Hash chiave pubblica)
```

L'hash della chiave pubblica viene poi compressa in una forma più breve e facile da usare e può essere ulteriormente elaborata in differenti tipologie di indirizzi bitcoin:

```mermaid { align="center" zoom="false" }
---
title:
---
graph LR;
A(Hash chiave pubblica) --> B(Base58Check)
B(Base58Check)          --> |A = 26-35 char| C(Indirizzo bitcoin)
```

1. **Indirizzi P2PKH (Pay-to-PubKey-Hash)**:
    
    - Prefisso: Cominciano con il numero `1`.
    - Descrizione: Sono il tipo più tradizionale e uno dei primi formati utilizzati nel protocollo Bitcoin.
    - Caratteristiche: Gli indirizzi P2PKH richiedono che una transazione venga firmata con una chiave privata corrispondente alla chiave pubblica hashata. Questo tipo di indirizzo è ampiamente supportato da tutti i wallet e gli exchange.
    - Esempio: `1A1zP1eP5QGefi2DMPTfTL5SLmv7DivfNa`.

2. **Indirizzi P2SH (Pay-to-Script-Hash)**:
    
    - Prefisso: Cominciano con il numero `3`.
    - Descrizione: Introdotti con Bitcoin Improvement Proposal (BIP) 16 nel 2012, gli indirizzi P2SH sono stati creati per permettere l'uso di script Bitcoin più complessi, come portafogli multi-firma o condizioni di spesa personalizzate.
    - Caratteristiche Piuttosto che verificare direttamente la chiave pubblica, questi indirizzi richiedono l'esecuzione di uno script associato alla transazione, che permette di implementare funzionalità come le transazioni multi-firma.
    - Esempio: `3J98t1WpEZ73CNmQviecrnyiWrnqRhWNLy`.

3. **Indirizzi Bech32 (SegWit)**:
    
    - Prefisso: Cominciano con `bc1`.
    - Descrizione Introdotti nel 2017 con l'aggiornamento SegWit (Segregated Witness), proposto in BIP 173, questi indirizzi sono progettati per migliorare l'efficienza delle transazioni Bitcoin.
    - Caratteristiche: Gli indirizzi Bech32 riducono il peso delle transazioni, rendendo le commissioni più economiche e migliorando la velocità delle transazioni. Inoltre, migliorano la sicurezza grazie a un formato che riduce il rischio di errori umani nella digitazione degli indirizzi.
    - Esempio: `bc1qw508d6qejxtdg4y5r3zarvaryvg6kdaj`.

4. **Indirizzi Taproot (Bech32m)**:
    
    - Prefisso Cominciano anch'essi con `bc1`, ma differenziabili per il prefisso "bc1p".
    - Descrizione: Introdotti nel novembre 2021 con l'aggiornamento Taproot, questi indirizzi utilizzano il formato Bech32m, che è un miglioramento delle funzionalità esistenti per supportare nuove tipologie di firme e smart contract.
    - Caratteristiche: Gli indirizzi Taproot migliorano la privacy e l'efficienza delle transazioni complesse, come quelle multi-firma o che richiedono condizioni specifiche di spesa. Consentono inoltre di raggruppare diverse condizioni in una singola chiave pubblica, riducendo i dati rivelati sulla blockchain.
    - Esempio: `bc1p4za7ax9zq0gw4s4jr4k8m6q3w0jf6l7c30a`.

Anche se un indirizzo bitcoin è visibile pubblicamente sulla blockchain, non è direttamente collegato ad una persona specifica, il che garantisce un alto grado di anonimato. Tuttavia, se un indirizzo viene riutilizzato frequentemente e collegato ad un'identità, può essere possibile tracciare le transazioni e compromettere la privacy dell'utente. Per questo motivo, è una pratica comune creare nuovi indirizzi per ogni transazione.