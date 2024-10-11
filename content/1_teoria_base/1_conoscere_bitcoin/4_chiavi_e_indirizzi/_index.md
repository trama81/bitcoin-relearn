+++
title = 'Chiavi e indirizzi'
author = 'me'
date = 2024-10-05
weight = 4
draft = true
+++

> [!important] Brief:
> Questa sezione ti aiuterà a capire cosa sono le chiavi private, le chiavi pubbliche e che relazione c'è tra di esse.

# Chiavi
## Chiave privata

La chiave privata è un numero casuale, che si può ottenere per esempio lanciando una moneta 256 volte (o con una fonte di entropia o casualità equivalente) e annotando via via le cifre binarie (dove per esempio: testa=1, croce=0).

Nella pratica, la chiave privata viene generata da un algoritmo detto _entropia_, che viene alimentato da una sorgente di caos e genera un output mnemonicamente rappresentato da 12 o 24 parole seme, dette _seed phrase_. La conoscenza dalla seed phrase è l'__unico modo__ per ricostruire la chiave privata.

La chiave privata è l’elemento crittografico che permette al possessore di bitcoin di spenderlo: viene utilizzata per creare _firme digitali_, dimostrando la proprietà dei fondi in una transazione, che sono necessarie per trasferire i bitcoin.

__La chiave privata deve rimanere segreta in ogni momento__, perché rivelarla a terzi equivale a dare loro il controllo sui bitcoin associati a quella chiave. Deve essere anche protetta da perdite accidentali, perché __se persa non può essere recuperata e i fondi associati ad essa saranno anch’essi persi per sempre__.

È possibile crittografare la chiave privata con una _passphrase_ in modo che possa essere archiviata, trasportata o conservata in modo sicuro, anche qualora la chiave fosse esposta.
Una chiave crittografata con passphrase, se decodificata con la stessa passphrase può essere utilizzata in qualsiasi [[1.8 Wallet]].

La chiave privata sarà costudita all’interno del wallet, il quale fornirà anche una copia di backup (sottoforma di _Seed Phrase_) che sarà l’unico elemento con cui si potrà recuperare l’accesso ai fondi qualora il wallet andasse distrutto o rubato.


## Chiave pubblica

La chiave pubblica viene calcolata a partire dalla chiave privata utilizzando la crittografia asimmetrica, che rende irreversibile questa operazione.

Il proprietario della chiave privata può tranquillamente creare una chiave pubblica e condividerla con chiunque, sapendo che nessuno può invertire la funzione e risalire alla chiave privata.

In una transazione, la chiave pubblica del beneficiario identifica univocamente il destinatario, senza tuttavia rivelarne l'anagrafica.


# Indirizzi
## Indirizzi bitcoin

L'indirizzo viene calcolato a partire dalla chiave pubblica utilizzando la crittografia asimmetrica, che rende irreversibile questa operazione.

L’indirizzo bitcoin è quello che appare comunemente in una transazione come il destinatario dei fondi. Nella pratica è però sconsigliato ricevere fondi sempre sullo stesso indirizzo, poichè questo introduce un problema di privacy: poichè la blockchain è pubblica, ricercando la chiave pubblica si può ricercare la chiave pubblica e trovare tutto lo storico delle transazioni, venendo a scoprire il saldo.

La soluzione a questo problema di privacy viene risolto sempre grazie alla crittografia, che a partire dalla stessa coppia di chiavi (privata e pubblica), è in grado di calcolare in modo deterministico una lista di indirizzi anonimi.