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

