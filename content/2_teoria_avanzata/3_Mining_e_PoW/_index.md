+++
title = 'Mining e PoW'
weight = 3
draft = true
+++

### # Mining e PoW: come funzionano

Sì, sappiamo che con il **mining** si producono i Bitcoin. Ci sono dei computer, delle “macchine” che consumano energia per mantenere sicura la blockchain, ma esattamente questo processo come funziona? E come viene eseguito?

Lo scopriremo in questa nuova sezione del nostro corso base su Bitcoin, crypto, blockchain e dintorni, dove andiamo a indagare quelli che vengono chiamati “**algoritmi di consenso**”. Quegli algoritmi che permettono ai vari nodi che fanno parte di un **network** (da cui dipende la sicurezza della blockchain) di “andare d’accordo” su un’unica soluzione, e soprattutto di rimanere sempre integri, evitando che vengano attaccati e manomessi d’attori malevoli.

È importantissimo quindi studiarli, perché sono i **fondamenti sui quali si basa il funzionamento e la sicurezza di Bitcoin** e delle altre criptovalute. 

Il mining stesso può essere inteso in sé stesso come il più importante nonché longevo algoritmo di consenso distribuito, e colonna portante del mondo crypto, in quanto è **ciò che gli permette di esistere**, come fosse il suo cuore pulsante. E soprattutto, è ciò che gli permette di essere sicuro, in relazione alla blockchain. Senza sicurezza, infatti, una criptovaluta non ha ragion d’essere.

Cercheremo quindi di capire che cos’è un algoritmo di consenso distribuito e a che cosa serve, per poi andare nello specifico esplorando il mondo del **proof-of-work (PoW)**, che di fatto “è” il mining, e uno degli algoritmi di consenso distribuito esistenti nel mondo blockchain.

### # Il proof-of-work (PoW)

Il meccanismo PoW funziona (come si potrebbe intuire) grazie al “**lavoro**”, che è da intendersi come dimostrazione di un determinato consumo di energia, derivato a sua volta dallo sfruttamento di un tot di **potenza di calcolo** impegnato in una determinata versione della blockchain. 

Questo lavoro, di conseguenza, funge anche da **validazione** per ognuno dei nodi che competono nella blockchain, che fanno a gara per “risolvere” un determinato blocco di transazione. 

A questo punto resta da provare che il lavoro svolto per “chiudere” questo blocco sia stato fatto effettivamente, e **senza andare ad aggirare il consenso distribuito**. In caso contrario, infatti, ognuno potrebbe inventarsi da sé dei blocchi di transazione. 

Per capire come funziona il mining **occorre in primo luogo comprendere come funziona l’hash**, ovvero una funzione che prende un dato input e lo trasforma in un output (l’hash, appunto), in forma di stringa alfanumerica. Questa non è una striscia casuale, in quanto lo stesso input risulta sempre nello stesso output. In questo modo, non c’è nessun modo a partire dall’hash di risalire all’origine, ma se si conosce quest’ultima, allora si può anche verificare che sia corretto, testando in un secondo momento l’output. 

La funzione si definisce, proprio per questo motivo, “**asimmetrica**”, perché dall’output non si può risalire all’input. In questo senso, l’unico modo per risalire all’input dall’output è provare infiniti input, finché questo non viene “azzeccato”. Questi passaggi sono fondamentali per **comprendere la funzione di hashing**, alla base del mining. In parole semplici, si prende un dato, lo si da in pasto alla funzione, e si ottiene un output, da cui è impossibile risalire all’origine se non per infiniti tentativi.

### Il ruolo del miner

Il PoW, in sostanza, chiede tramite questo meccanismo ai miner di risolvere un **complesso calcolo probabilistico**, e il primo a riuscirci, validando il blocco in questione, ottiene anche la sua ricompensa. Per risolvere il calcolo, i miner di successo utilizzano speciali computer chiamati **ASIC**, che non fanno altro che provare in continuazione delle combinazioni di numeri e lettere (crittografia **SHA-256**) fino al momento in cui non viene risolto il problema proposto. 

Tutto ciò, se non fosse ancora chiaro, serve appunto per **impedire manomissioni del network**, e poiché la validazione comporta spese ingenti in macchinari ed energia elettrica, non sarebbe conveniente agire in modo malevolo, (si perderebbero solo dei soldi). Maggiore è la potenza di calcolo a disposizione, quindi, superiori saranno le possibilità di battere sul tempo tutti gli altri miner. Alla validazione del blocco, il vincitore riceve una certa quantità di Bitcoin come ricompensa, e la soluzione viene distribuita agli altri nodi. È qui che il sistema chiude il cerchio e ha senso: l’**incentivo economico** spinge a partecipare, e l’emissione di un nuovo blocco **crea nuovi BTC**, azione nota con il termine “mining” proprio perché, di fatto, si “estraggono” nuovi esemplari della moneta. Oggi, il 90% di questa criptovaluta è già in circolazione. Ogni quattro anni, il fenomeno chiamato halving dimezza l’emissione, e gli ultimi Bitcoin verranno minati nel 2140. 

In sintesi, il proof-of-work richiede come “stake” la potenza computazionale e, di conseguenza, anche un certo dispendio energetico. Chi sostiene questa spesa ha tutto l’interesse a fare le cose per bene e, grazie alla sua costruzione, garantisce che **nessuna transazione errata possa farla franca**. E alla validazione del blocco, nuovi Bitcoin (o altre crypto) vengono emessi.


