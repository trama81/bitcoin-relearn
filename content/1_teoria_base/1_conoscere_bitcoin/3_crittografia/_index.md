+++
title = 'Crittografia'
author = 'me'
date = 2024-10-05
weight = 3
draft = true
+++

> [!important] Brief:
> Questa sezione ti aiuterà a capire cos'è bitcoin e a familiarizzare con le basi del suo funzionamento.


Il bitcoin è basato su *crittografia*: una branca della matematica ampiamente usata in sicurezza informatica, che permette di dimostrare la conoscenza di un segreto (chiave privata) senza doverlo rivelare e di provare l’autenticità dei dati (firma digitale).

> _La sicurezza di un sistema crittografico non deve dipendere dal tenere celato l'algoritmo, ma solo dal tenere celata la chiave._
> 
> _Auguste Kerchoffs_


La crittografia è utilizzata anche per creare una coppia di chiavi che controlla l’accesso ai bitcoin; tale coppia è formata da una chiave privata e, derivata da essa, un’unica chiave pubblica. La chiave pubblica è usata per ricevere i fondi, mentre la chiave privata è usata per autorizzare le transazioni in uscita.

La crittografia consente di generare firme digitali. La chiave privata può essere utilizzata per firmare digitalmente una transazione e tale firma digitale può essere effettuata solamente da chi è a conoscenza della chiave privata (che non viene mai rivelata e non è ricavabile a partire dalla firma digitale). 

Dal punto di vista della blockchain, chiunque abbia accesso alla chiave pubblica e alla firma della transazione le può usare per verificare la firma stessa. Questa proprietà della crittografia rende possibile a chiunque la verifica delle firme in ogni transazione, assicurando allo stesso tempo ai proprietari delle chiavi private di produrre firme valide.