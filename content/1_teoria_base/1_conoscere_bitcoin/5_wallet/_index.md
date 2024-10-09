+++
title = 'Wallet'
author = 'me'
date = 2024-10-05
weight = 5
draft = true
+++

## Portafogli

In sintesi, i portafogli sono contenitori di chiavi private.

Più in generale, il portafoglio è un applicazione che funge da interfaccia primaria per l’utente. Il portafoglio controlla l’accesso ai fondi dell’utente, gestendo le chiavi e gli indirizzi, tenendo traccia del bilancio, e creando e firmando le transazioni.

Un portafoglio bitcoin contiene una raccolta di coppie di chiavi, ognuna composta da una chiave privata e una pubblica. La chiave privata (k) è un numero, di solito scelto a caso. Dalla chiave privata, viene utilizzata la moltiplicazione a curva ellittica, una funzione di crittografia unidirezionale, per generare una chiave pubblica (K). Dalla chiave pubblica (K), viene utilizzata una funzione di hash crittografico unidirezionale per generare un indirizzo bitcoin (A).

Il rapporto tra la chiave privata, la chiave pubblica e l’indirizzo bitcoin è mostrato in Figura