+++
title = 'Transazioni'
author = 'me'
date = 2024-10-05
weight = 5
draft = true
+++

Le transazioni bitcoin richiedono che una firma digitale (witness) valida sia inclusa nella blockchain, che può essere generata solo con una chiave privata (segreta); quindi, chiunque abbia una copia di quella chiave ha il controllo dei bitcoin.

C’è una relazione matematica tra la chiave pubblica e quella privata che permette alla chiave privata di essere usata per generare firme sui messaggi. Questa firma può essere validata attraverso la chiave pubblica senza rivelare la chiave privata.

Quando si spendono bitcoin, il proprietario attuale dei bitcoin presenta la sua chiave pubblica e una firma (differente ogni volta, ma creata dalla stessa chiave privata) in una transazione per autorizzare il rilascio di quei bitcoin. Attraverso la presentazione della chiave pubblica e della firma, tutti i membri della rete bitcoin possono verificare e accettare la transazione come valida, confermando che la persona che trasferisce i bitcoin li ha posseduti al momento del trasferimento.