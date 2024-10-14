+++
title = 'Blockchain'
weight = 2
draft = true
+++

Come può la blockchain ottenere la decentralizzazione, la **sicurezza**, **l’immutabilità**, la **trasparenza** e tutte le caratteristiche che la rendono unica? Lo scopriamo in questo capitolo del corso base sul mondo crypto, in maniera semplice ma completa, senza trascurare nessuno dei dettagli più importanti.

### # La dipendenza blockchain/criptovalute

Criptovalute e blockchain **non potrebbero esistere l’una senza l’altra**. Se la criptovaluta è l’unità di valore digitale che viene scambiata su un’infrastruttura, la blockchain non è che quest’ultima, per l’appunto. Occorre quindi capire che cos’è, se si vuole capire in fondo la dinamica dell’esistenza, dello spostamento, e del mantenimento delle criptovalute.

La **blockchain** è definita generalmente come “**registro distribuito**”. Non è, a conti fatti, che un database con caratteristiche particolari.  E la prima è l’essere custodita e aggiornata in tempo reale su una moltitudine di nodi distribuiti per il mondo. Questi devono essere sempre online e attivi, e consentono alla blockchain di essere sicura, trasparente e consultabile da tutti, rendendo impossibili le modifiche su transazioni passate (le privacy coin sono un capitolo a parte, poiché le blockchain principali sono pubbliche e trasparenti).

L’unità funzionale della blockchain è il “**blocco**”, che ogni tot viene aggiunto e distribuito, e la cui creazione dipende dal tipo di chain. Per Bitcoin sono circa **10 minuti**, ma possono essere anche nanosecondi o ore.

### La decentralizzazione

La decentralizzazione fa si che la blockchain sia **distribuita su una moltitudine di nodi**, ognuno dei quali deve contenere tutta la sua “storia”. Se si volesse creare un **full-node** (un nodo con tutte le sue funzionalità), questo deve avere salvata in locale una copia dell’intera blockchain. Se il nodo non fosse aggiornato, a questo sarebbe richiesto una sincronizzazione perché poi possa procedere con il lavoro proprio di un nodo. 

La decentralizzazione è importante anche da un punto di vista di “**consenso**“. Tutti i nodi devono essere d’accordo sulla stessa versione della blockchain, e da questo deriva anche un tema legato alla sicurezza. 

Ma cosa contiene effettivamente un blocco? La risposta sta nelle **transazioni**, che se non si limitano alla capienza di un singolo ne coinvolgono anche altri. Perché tutta la macchina possa funzionare, entrano in gioco poi le fee (o commissioni) di transazione, tramite le quali i “**miner**” vengono ricompensati (oltre ai premi erogati da ogni blocco in forma di Bitcoin, in questo caso).

All’interno di un blocco sono comprese le transazioni in un ordine dettato dal valore della fee per la quale è stata effettuata, più tutte le transazioni e i dati del blocco precedente. Ciò è importante per la sicurezza, perché si crea una serie, e perché **se un attore malevolo volesse modificare un blocco precedente dovrebbe conseguentemente modificare anche tutti quelli successivi ad esso**. Quelli che seguono, infatti, andrebbero a invalidare tutta la catena. Un blocco, per questa ragione, più riceve dei suoi simili in coda, più diventa difficile da falsificare. E più conferme ci sono, più una transazione risulta **irreversibile**. Validato un nuovo blocco, questo viene dato in pasto al network, che lo valida e lo propaga a tutti gli altri. E quando il blocco viene distribuito, questi si sincronizzano.

E come si mantiene la decentralizzazione? Come influisce, per esempio, un nodo più “potente” degli altri, e come esercita questo potere? Una maggiore decentralizzazione impone che **lo stesso nodo debba avere meno probabilità di validare i blocchi in proporzione a un determinato periodo di tempo**. E questo meccanismo dipende dall’algoritmo di consenso. Un maggior numero di nodi è sintomo di maggiore decentralizzazione, ma serviranno sempre nuovi nodi che competano per validare gli ultimi arrivati, anche in virtù del fatto che saranno sempre di più.

Inoltre, anche la **sicurezza** è legata a doppio filo con la decentralizzazione. Perché tutto il sistema funzioni è necessario mettere d’accordo il network su un’unica versione della blockchain. Non possono infatti esistere nodi che comprendano varie versioni. E la sicurezza è proporzionale alla decentralizzazione, e quindi al **numero dei partecipanti al network**. In ultima istanza, un nodo non deve essere in grado di manomettere la blockchain, altrimenti potrebbe prenderne il controllo. 

Se una blockchain ha la maggioranza di nodi corretti, funziona bene, altrimenti l’alternativa malevola sarà vista come quella giusta. Interessi sapere, per ora, che i punti fondamentali per la decentralizzazione e la sicurezza sono l’**incentivo di far sì che non esista un gruppo dominante di nodi**, e ci sia sempre un incentivo a crearne di nuovi, per far si che la decentralizzazione possa solo crescere.

### Come funziona una transazione

Se si vuole inviare Bitcoin, bisogna “generare” una transazione, divisibile sotto un lato tecnico in “**input**” e “**output**”. Esistono i wallet adibiti a questa funzione, e l’inserimento di un address genera quella che si chiama transazione, anche prima che questa venga effettuata. La transazione, in sostanza, è una stringa che contiene input e output, una quantità di BTC e la direzione verso un indirizzo relativo. Una volta avuti questi elementi, si firma il tutto con la propria **chiave privata**, e questa transazione diventa “**firmata**” e inviata alla blockchain, che a sua volta la validerà. Se la transazione non fosse firmata, non verrebbe validata, e per firmarla è necessaria la propria chiave privata. 

Una caratteristica potente della firma è il fatto che **il validatore può controllare che il firmatario sia realmente il proprietario di quella transazione**. La transazione proviene da un address, a cui è associata una chiave privata che non è mai esposta. Il validatore deve poter validare la transazione verificando che la firma sia quella corretta senza l’esposizione della chiave privata. Ed è possibile grazie alla crittografia. Una volta fatto ciò la blockchain la includerà nel blocco e la validerà, distribuendola.

Una transazione include quindi input, output e altri dati. Gli **input** sono l’insieme di address e “valore” delle **transazioni ricevute e non spese** (si può spendere solo “ciò che si è ricevuto”, nel linguaggio della blockchain), come un output precedente che non si è speso, e ci sono dei dati sull’autenticità dell’input e sulla firma della transazione. Una sorta di assegno con una firma, ma meno da boomer.

Nell’**output** c’è invece l’address del destinatario e i BTC inviati. Insieme a ciò che viene chiamato “**change**”, ovvero l’eccedenza dell’input rimandata indietro. E ovviamente la fee, che determina quanta priorità dare nella coda delle transazioni. 

Se si è in possesso un BTC, ma si vuole inviarne 0,3, si spenderà quell’output da un BTC, ma generandone due: 0,3 BTC da inviare al destinatario, e 0,7 BTC verso sé stessi: una complicazione è derivata da una questione di sicurezza e di **gestione ottimale delle transazioni**. Un output, quando speso, non può essere fatto parzialmente, e genera quindi un output “unspent”, che in futuro si potrà riutilizzare. 

Nella blockchain è possibile ripercorrere a ritroso tutte le transazioni, fino ad arrivare all’origine dei BTC spostati. Se si andasse poi a vedere da dove arrivano i propri BTC, si potrebbe vedere tutto lo **storico delle transazioni fino a quella di origine** o di mining, anche detta “coinbase transaction”. Ogni blocco genera tot bitcoin, creati dal nulla, e che rappresentano le transazioni d’origine.