+++
title = 'Crittografia'
author = 'me'
date = 2024-10-12
weight = 3
draft = false
+++

> [!important] Brief:
> Questa sezione ti aiuterà a capire cos'è la crittografia e perchè è un concetto fondamentale per bitcoin e per la blockchain.


Il bitcoin è basato su *crittografia*: una branca della matematica ampiamente usata in sicurezza informatica, che permette di dimostrare la conoscenza di un segreto (chiave privata) senza doverlo rivelare e di provare l’autenticità dei dati (firma digitale).

> _La sicurezza di un sistema crittografico non deve dipendere dal tenere celato l'algoritmo, ma solo dal tenere celata la chiave._
> 
> _Auguste Kerchoffs_

La crittografia a doppia chiave, comunemente nota come _crittografia asimmetrica_, è un sistema di crittografia che utilizza due chiavi diverse: una chiave pubblica e una chiave privata.

Ecco come funziona:

1. **Chiavi**:
    
    - **Chiave pubblica**: È accessibile a chiunque e può essere condivisa liberamente. Viene utilizzata per crittografare i dati.
    - **Chiave privata**: Deve rimanere segreta e conosciuta solo dal proprietario. Viene utilizzata per decrittografare i dati.

2. **Processo di crittografia**:
    
    - Quando qualcuno desidera inviare un messaggio sicuro a una persona (ad esempio, Alice), utilizza la chiave pubblica di Alice per crittografare il messaggio. Questo garantisce che solo Alice possa leggerlo, poiché solo lei ha accesso alla sua chiave privata.

3. **Processo di decrittografia**:
    
    - Una volta che Alice riceve il messaggio crittografato, utilizza la sua chiave privata per decrittografarlo. Solo la chiave privata corrispondente alla chiave pubblica utilizzata per crittografare il messaggio può decifrare il contenuto.

4. **Sicurezza**:
    
    - La sicurezza della crittografia asimmetrica si basa sulla difficoltà di calcolare la chiave privata a partire dalla chiave pubblica. Anche se qualcuno conosce la chiave pubblica, non è in grado di ottenere la chiave privata o di decifrare i messaggi crittografati senza di essa.

5. **Firmare digitalmente**:
    
    - Oltre alla crittografia, la crittografia asimmetrica consente anche la firma digitale. Alice può "firmare" un messaggio con la sua chiave privata, e chiunque può verificare l'autenticità della firma utilizzando la chiave pubblica di Alice. Questo assicura che il messaggio provenga effettivamente da Alice e non sia stato alterato.

In sintesi, la crittografia a doppia chiave consente comunicazioni sicure e autenticazione, rendendo difficile l'intercettazione e la falsificazione delle informazioni.

Dal punto di vista della _blockchain_, questa proprietà della crittografia rende possibile a chiunque la verifica delle firme in ogni transazione, assicurando allo stesso tempo ai proprietari delle chiavi private di produrre firme valide.