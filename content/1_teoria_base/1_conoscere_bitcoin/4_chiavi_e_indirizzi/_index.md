+++
title = 'Chiavi e indirizzi'
author = 'me'
date = 2024-10-13
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


# Indirizzi
### Indirizzi bitcoin

L'indirizzo viene calcolato a partire dalla chiave pubblica utilizzando la [*crittografia asimmetrica*](https://trama81.github.io/bitcoin/1_teoria_base/1_conoscere_bitcoin/3_crittografia/index.html), che rende irreversibile questa operazione.

L’indirizzo bitcoin è quello che appare comunemente in una transazione come il destinatario dei fondi. Nella pratica è però sconsigliato ricevere fondi sempre sullo stesso indirizzo, poichè questo introduce un problema di privacy: poichè la blockchain è pubblica, si può ricercare la chiave pubblica e trovare tutto lo storico delle transazioni, venendo a scoprire il saldo.

La soluzione a questo problema di privacy viene risolto sempre grazie alla crittografia, che a partire dalla stessa coppia di chiavi (privata e pubblica), è in grado di calcolare in modo deterministico una lista di indirizzi anonimi.


