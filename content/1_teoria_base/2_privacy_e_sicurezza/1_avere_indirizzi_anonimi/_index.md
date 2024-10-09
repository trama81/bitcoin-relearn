+++
title = 'Avere indirizzi anonimi'
author = 'me'
date = 2024-10-05
weight = 1
draft = true
+++

Premessa:
L'acquisto di Bitcoin attraverso un canale tracciabile (con KYC o con metodi di pagamento tracciabili) crea un'associazione indelebile tra la propria identità e l'indirizzo del wallet a cui tali Bitcoin vengono trasferiti.

Scopo:
definire un protocollo per trasferire i propri Bitcoin da degli indirizzi associati alla propria identità a dei nuovi indirizzi anonimi, ottenuti mediante l'inizializzazione di un nuovo wallet.

Importante:
il protocollo non prevede e non protegge il possessore dei Bitcoin, nel caso in cui quest'ultimo decida di non dichiarare i propri Bitcoin all'agenzia delle entrate. L'acquisto ed il possesso anonimi saranno descritti da un altro protocollo specifico.

Scenario 1 di partenza:

Banca ---bonifico---> IBAN BINANCE ---acquistoBTC--->INDIRIZZO BINANCE ---send--->INDIRIZZO WALLET LEDGER (+Ledger Live)

Tizio possiede un UTXO che ha ricevuto un saldo da un indirizzo associato alla propria identità, poichè conscendo l'identità associata all'INDIRIZZO BINANCE è possibile associarla all'INDIRIZZO WALLET. Non si ha la certezza, ma soprattutto nel caso di acquisti ricorrenti è verosimile pensare che l'INDIRIZZO WALLET sia di Tizio.

_C'è modo di avere la certezza che i vari INDIRIZZO WALLET sono tutti generati a partire dalla stessa Chiave Pubblica Master, senza conoscere quest'ultima?_

_Conoscendo la Chiave Pubblica Master (ad esempio perchè l'abbiamo comunicata al commercialista), è possibile che lui possa conoscere tutti gli indirizzi che sono generati a partire da essa?_


Scenario 1.1:

INDIRIZZO WALLET LEDGER (+Ledger Live) ---send--->mINDIRIZZO WALLET COLDCARD (Sparrow)

Tizio acquista ed inizializza un nuovo wallet COLDCARD.
Se Tizio volesse transare da un indirizzo di un wallet potenzialmente tracciato, metterebbe a rischio la propria privacy? E potrebbe anche mettere a rischio la privacy del nuovo COLDCARD?

La risposta è che la lista di indirizzi generati dal wallet coldcard non sono riconducibili alla stessa identità associata al wallet ledger.
Pure nel caso in cui si facessero transazioni che potrebbero far pensare che l'identità dietro ai due wallet sia la stessa, non vi sarebbe la possibilità di provarlo con certezza. Infatti, il proprietario dei fondi, dal passaggio tra ledger e coldcard potrebbe dichiararli come "spesi", poichè non vi sarebbe modo di provare l'identità degli indirizzi generati dal wallet coldcard.
Attenzione però, che se continuassi a dichiarare tali fondi anche una volta trasferiti al coldcard, sarebbe come ammettere implicitamente che l'identità associata ai nuovi indirizzi sia sempre la stessa (altrimenti avrei dovuto dichiararli come "spesi").

Perchè allora usare due wallet? Perchè non spedire i fondi a dei nuovi indirizzi generati sempre a partire dal wallet ledger, dato che ogni indirizzo nuovo è anonimo?
La risposta è che, se qualche entità o persona (per esempio il commercialista) fosse a conoscenza della chiave pubblica master, potrebbe deterministicamente calcolare l'intera lista di indirizzi generabili dal ledger, e quindi potrebbe monitorare tutti gli indirizzi, compresi quelli non ancora usati, posseduti dal proprietario del ledger.




Scenario 1.2:

# Attenzione! Il rimescolamento presentato in questo paragrafo non è necessario, poichè gli indirizzi generati dal proprio Coldcard sono già anonimi grazie alla crittografia unidirezionale. L'unica accortezza che bisognerà avere è quella di non rivelare mai a nessuno la chiave pubblica master del coldcard. Bisogna poi decidere come dichiarare i fondi qui trasferiti, poichè se non dichiarati come "spesi", vuol dire ammettere implicitamente che quell'indirizzo appartiene sempre alla stessa persona; quindi per l'anonimato sarei al punto di partenza, ma nessuno potrebbe conoscere eventuali nuovi indirizzi generati dal wallet coldcard.

Tizio vuole assolutamente (con certezza assoluta) che i nuovi indirizzi COLCARD ricevano fondi da un'origine non associata/associabile alla propria identità. Quindi, chi invia i soldi deve essere una fonte già anonima o deve essere un'altra persona sconosciuta.

- Old_W_1, New_W_1
- Old_W_2, New_W_2
- Old_W_3, New_W_3
- Old_W_4, New_W_4

- Old_W_1 ---> New_W_2 (consolidamento UTXO)
- Old_W_2 ---> New_W_3 (consolidamento UTXO)
- Old_W_3 ---> New_W_4 (consolidamento UTXO)
- Old_W_4 ---> New_W_1 (consolidamento UTXO)
- -
- Old_W_1 ---> New_W_3 (consolidamento UTXO)
- Old_W_2 ---> New_W_4 (consolidamento UTXO)
- Old_W_3 ---> New_W_1 (consolidamento UTXO)
- Old_W_4 ---> New_W_2 (consolidamento UTXO)
- -
- Old_W_1 ---> New_W_4 (consolidamento UTXO)
- Old_W_2 ---> New_W_1 (consolidamento UTXO)
- Old_W_3 ---> New_W_2 (consolidamento UTXO)
- Old_W_4 ---> New_W_3 (consolidamento UTXO)