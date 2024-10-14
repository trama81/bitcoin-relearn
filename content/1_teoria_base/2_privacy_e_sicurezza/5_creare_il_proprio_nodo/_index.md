+++
title = 'Creare il proprio nodo'
author = 'me'
date = 2024-10-05
weight = 5
draft = false
+++

> [!important] Brief:
> Questa sezione ti guiderà nella preparazione di un nodo bitcoin personale e a familiarizzare con le basi del suo funzionamento.

### Perchè possedere un nodo privato

Operare con Bitcoin tramite un nodo privato ti permette di avere il pieno controllo delle tue transazioni e dei tuoi fondi, proteggendo la tua privacy in modo più efficace rispetto all'uso di servizi di terze parti. Con un nodo privato, non dipendi da intermediari per verificare le transazioni, evitando che i tuoi dati personali vengano tracciati o esposti. Inoltre, contribuisci alla sicurezza e alla decentralizzazione della rete Bitcoin, senza affidarti a piattaforme che potrebbero monitorare o censurare le tue attività. In sintesi, un nodo privato ti offre maggiore autonomia, sicurezza e privacy.

# Hardware necessario

Acquistare un mini PC per creare il proprio nodo Bitcoin è una scelta vantaggiosa poichè sono compatti, silenziosi e richiedono poca energia, il che li rende ideali per un funzionamento continuo senza incidere troppo sui consumi elettrici.

Sono qui proposte due soluzioni, che ho personalmente provato e che mi sento di consigliare:

{{< tabs title="Mini PC:" >}}
{{% tab title="HP EliteDesk 800 G3" %}}
### HP EliteDesk 800 G3
Dispositivi ricondizionati sono facilmente reperibili online (Amazon ed Ebay). Si consiglia l'acquisto separato di un SSD NVMe PCIe3.0 da almeno 2TB, che sarà poi da installare all'interno del mini PC.

![targets](img/HP_EliteDesk_800_G4_35W_miniPC.png)

| CPU   | Intel Core i5 gen6 - 2.4GHz                          |
| ----- | ---------------------------------------------------- |
| RAM   | 16GB DDR4                                            |
| SSD   | 1 slot SATA III 2.5'' 6GB/s, 1 slot M.2 NVMe PCIe3.0 |
| Power | DC 19.5V 3.33A - 65W                                 |
{{% /tab %}}

{{% tab title="Acemagic S1 N95" %}}
### Acemagic S1 N95
Facilmente reperibile su Amazon o sul [sito del produttore](https://acemagic.eu/products/s1-minipc). Si consiglia l'acquisto separato di un SSD NVMe PCIe3.0 da almeno 2TB, che sarà poi da installare all'interno del mini PC.

![targets](img/Acemagic_S1_N95_miniPC.png)

| CPU   | Intel Alder Lake N95 - 1.7GHz            |
| ----- | ---------------------------------------- |
| RAM   | 16GB DDR4                                |
| SSD   | 1 slot M.2 NVMe PCIe3.0, 1 slot M.2 SATA |
| Power | DC 12V 4A - 48W                          |
{{% /tab %}}
{{< /tabs >}}

---

# Installazione StartOS

### Scaricare StartOS

1) Cliccare su questo [link](https://github.com/Start9Labs/start-os/releases/)

2) Clicca sull'ultima release, taggata come "Latest"

	![targets](img/screen01.png)

3) Scorrere in fondo alla pagina e cliccare sul file che termina con "x86_64.iso"

	![targets](img/screen02.png)

### Creare una ISO di StartOS per il boot

4) Scaricare [Balena Hetcher](https://etcher.balena.io/#download-etcher)

5) Scorrere lungo la pagina e cliccare sul file relativo al proprio sistema operativo (il sistema operativo che si usa abitualmente sul proprio PC, __non__ il sistema operativo del full node)

6) Collegare una chiavetta USB al proprio PC

7) Avviare Balena Hetcher

	![targets](img/screen03.png)

8) Cliccare su "Flash from file" e selezionare il file di StartOS (con estensione .iso) scaricato precedentemente

9) Cliccare su "Select target" e selezionare la chiavetta USB (precedentemente collegata al PC)

10) Cliccare su "Flash!" e attendere il completamento


### Installare StartOS sul Nodo

11) Collegare monitor, tastiera, mouse e alimentazione al Nodo ed infine, collagare la chiavetta USB con la ISO di StartOS per il boot

12) Accendere il Nodo e, mentre si avvia (fin dai primi istanti dopo averlo acceso) premere ripetutamente il tasto <kbd>ESC</kbd> (o il tasto <kbd>F4</kbd>, o <kbd>F8</kbd>, in funzione dell'hardware utilizzato), fino a quando comparirà la schermata del BIOS

	![targets](img/screen04.png)

13)  Utilizzando i tasti freccia della tastiera, selezionare la scheda "Boot" e scorrere fino alla voce "Boot Option #1", quindi premere <kbd>INVIO</kbd> e selezionare la chiavetta USB inserita

14) Selezionare la scheda "Save & Exit", scorrere su "Save Changes and Exit" e premere <kbd>INVIO</kbd>

15) Attendere il riavvio e l'inizializzazione dell'installazione di StartOS, quindi selezionare l'SSD su cui effettuare l'installazione

	![targets](img/screen05.png)

16) Cliccare su "Install StartOS" e confermare cliccando CONTINUE

	![targets](img/screen06.png)
	![targets](img/screen07.png)

17) Attendere il completamento dell'installazione, quindi rimuovere la chiavetta USB dal Nodo e cliccare su REBOOT

	![targets](img/screen08.png)

18) Se tutto è andato a buon fine, comparirà questa schermata. Cliccare su "Start Fresh" e quindi selezionare l'SSD 

	![targets](img/screen10.png)
	![targets](img/screen11.png)

19) Inserire una password, ri-scriverla per conferma e quindi cliccare su FINISH.

	![targets](img/screen12.png)

20) Attendere l'inizializzazione di StartOS

	![targets](img/screen13.png)

21) Al termine dell'inizializzazione, sarà possibile loggarsi per accedere al proprio nodo

	![targets](img/screen14.png)
	![targets](img/screen15.png)

22) DESCRIVERE DI PRENDERE L'IP O L'HOST NAME


---

# Configurazione StartOS

### Accesso a StartOS da rete LAN

### Installazione di Bitcoin Core

### Installazione di Electrs

### Installazione di Mempool


---

# Preparazione del Wallet

### Installazione Sparrow Wallet

### Configurazione Sparrow Wallet

### Creazione/Importazione Wallet

### Collegamento del Ledger a Sparrow Wallet

Se ci troviamo in ambiente Linux Mint 22, per poter collegare con successo il Ledger Nano S Plus a Sparrow Wallet è necessario installare dei componenti che non sono inclusi di default nel sistema operativo.
Aprire il terminale (CTRL+ALT+T) ed inserire i seguenti comandi:

```bash
wget -q -O - https://raw.githubusercontent.com/LedgerHQ/udev-rules/master/add_udev_rules.sh | sudo bash
```
```bash
sudo add-apt-repository universe
```
```bash
sudo apt install libfuse2
```
### Transare tramite il proprio nodo