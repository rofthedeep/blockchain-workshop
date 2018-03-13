# Blockchain Workshop

## Die Blockchain Technology verstehen 

### Wie funktioniert das Grundprinzip hinter einer Blockchain

Link zum Code: [https://codesandbox.io/s/kmwmz353r3](https://codesandbox.io/s/kmwmz353r3)

- Eine Blockchain basiert auf vielen Blöcken
- ein Block werden mit verschiedenen Parametern generiert und bei erfolgreicher Berechnung am Ende der Blockchain angehangen
- der erste Block ist der "Genesis" Block. Für seine Anlage gibt es eine extra Funktion
- ein Block beinhaltet in unserem Beispiel folgende Daten:
	- der Index
	- Timestamp der Erstellung
	- Data: es kann Text oder andere Inhalte mitgeführt werden
	- den Hash des vorherigen Blocks (fälschungssicherheit)
	- der Hash des Blocks
- der Hash des neuen Blocks wird aus verschiedenen Parametern erzeugt (index, timestamp, previousHash)

So kann man in JS einfach seine erste Blockchain erzeugen.

### Proof of Work: So funktioniert Mining

- um das Minen von Blöcken entsprechend der Nachfrage schwieriger zu machen, muss man Rätsel lösen um einen Block erfolgreich zu erstellen
- diese Schwierigkeit kann ausgesteuert werden (difficulty)
- ein Kriterium: der Hash des nächsten Blocks muss mit zwei Nullen beginnen
- dafür wird eine Varible nach jedem misslungenen Versuch um 1 nach oben gezählt. So ändern sich die Parameter bei der Hash-Erzeugung

Das gerne ausprobieren: mit 4 Nullen geht der Editor z.B. schon in die Knie.

### Was noch fehlt

- Privater Schlüssel an Block: Wem gehört was?
- Contracts: Verträge auf Basis der Blockchain

### Vorbereiteter Test Code

- [https://codesandbox.io/s/kmwmz353r3](https://codesandbox.io/s/kmwmz353r3)

### Quellen

- [https://github.com/openblockchains/awesome-blockchains/tree/master/blockchain.js](https://github.com/openblockchains/awesome-blockchains/tree/master/blockchain.js)
- [https://github.com/openblockchains/awesome-blockchains](https://github.com/openblockchains/awesome-blockchains)

## Ein eigener Coin auf der Ethereum Plattform

### Präsentation

[Hier gibt es die Präsentation & Anleitung als PDF](https://github.com/rofthedeep/blockchain-workshop/raw/master/ethereum_smart_contracts.pdf)

### Benötigte Tools

- Eine aktuelle Nodejs Version (https://nodejs.org/en/)
- Ganache Blockchain Simulator (http://truffleframework.com/ganache/)
- Metamask Browser Wallet (https://metamask.io/)

### Schritt für Schritt Anleitung

* Führt `$ npm install -g truffle` im Terminal aus
* Erstellt euch einen Projektordner und wechselt mit `cd` in diesen
* Führt in diesem Ordner `truffle unbox toxin20/maincoin-box` aus, um euch den benötigten Projektcode zu ziehen.
* Mit `truffle compile` werden die Smart Contracts kompiliert
* Startet nun Ganache, um bei euch lokal auf dem Rechner eine Blockchain laufen zu lassen
* `truffle migrate` deployed den MainCoin Smart Contract auf eure lokale Blockchain. Danach sollte euch Ganache unter Current Block die Zahl 4 anzeigen (dies sind die Transaktion vom Contract Deployment)
* Mit `npm run dev` startet ihr den lokalen Webserver. Unter http://localhost:3000 ist anschließend das MainCoin Web Wallet zu erreichen.
* Nun müsst ihr noch Metamask in eurem Browser einrichten. Wählt im ersten Bildschirm von Metamask "Import existing DEN" aus, um den Seed zu importieren, den Ganache euch unter "Mnemonic" gibt. 

![Imgur](https://i.imgur.com/80NqxEg.png)

![Imgur](https://i.imgur.com/WfVVioR.png)

* Seed reinkopieren und ein Passwort vergeben

![Imgur](https://i.imgur.com/sJdSoAc.png)

* Im nächsten Schritt müssen wir Metamask statt mit dem richtigen Ethereum Hauptnetzwerk mit eurer lokalen Ganache Blockchain Instanz verbinden (Netzwerk "Custom RPC" auswählen)

![Imgur](https://i.imgur.com/Tg7yVrg.png)

* Adresse einfügen und "Save" klicken

![Imgur](https://i.imgur.com/KX6DVny.png)

* Wenn alles geklappt hat seid ihr mit eurer lokalen Blockchain verbunden und eure Balance sollte irgendwas zwischen 99 und 100 ETH sein.

![Imgur](https://i.imgur.com/7kIHIdG.png)

* Eine Aktualisierung des Web Wallets unter http://localhost:3000 sollte euch nun eure MainCoin Balance anzeigen. Ihr könnt das Wallet nutzen, um MainCoins auf der (simulierten) Blockchain hin und her zu schicken.

![Imgur](https://i.imgur.com/1P4l6Wr.png)

### Nächste Schritte

Als nächstes könntet ihr zum Testen in einem echten Netzwerk den Smart Contract zum Beispiel auf das Ropsten Test Network deployen. 
