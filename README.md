

# Interledger internals

<div style="height: 20px;"></div>
<center><img src="graphics/1ff7ef605d.png"></center>
<div style="height: 20px;"></div>



Деньги судя по всему перемещаются не по схеме: отправитель-получатель, а по схеме: отправитель-коннектор-...-коннектор-получатель, т.е. каждая нода по очереди передает другой определенную сумму, если сделка состоялась
Атомарный и универсальные режимы:
The Interledger protocol can be implemented in two modes: atomic mode and universal mode. In atomic mode, notaries are incorporated into the system. They are an ad-hoc group that is used to verify and validate transactions. Typically, atomic modes take place between trusted connector nodes between banks or financial service companies that might relate to each other.

The universal mode does not require notaries and can work between untrusted connectors. It uses Ripple’s internal cryptocurrency, XRP, to facilitate transfers. The transfer is accompanied by time constraints. If it does not take place within a certain timeframe, then the transaction is annulled.
Адресация:
https://interledger.org/developers/rfcs/ilp-addresses/
Брал из статьи про архитектуру: 
https://interledger.org/developers/rfcs/interledger-architecture/
Информация по нодам:
When two parties want to do business online, the one who sends money is the sender and the one who gets money is the receiver. If the sender and the receiver don't have some monetary system in common, they need one or more parties to connect them. In the Interledger architecture, connectors forward money through the network until it reaches the receiver.

Diagram showing Sender linked to two Connectors and a Receiver in a line

Within these specifications, we use node as a general term for any participant in the Interledger. A node may be a sender, a receiver, or a connector. The node may represent a person or business, or perhaps a single device or software program. In the case where a node represents a device or software program, the node is usually connected to another node that represents the device's owner or the person running the software.

You can envision the Interledger as a graph where the points are individual nodes and the edges are accounts between two parties. Parties with only one account can send or receive through the party on the other side of that account. Parties with two or more accounts are connectors, who can facilitate payments to or from anyone they're connected to.

Connectors provide a service of forwarding packets and relaying money, and they take on some risk when they do so. In exchange, connectors can charge fees and derive a profit from these services. In the open network of the Interledger, connectors are expected to compete among one another to offer the best balance of speed, reliability, coverage, and cost.
Вообще на сайте документации дается следующая информация:
The Interledger protocol suite sits atop a level which we call "ledger protocols". This level represents the existing money systems that Interledger connects. Even though they are not strictly part of the Interledger protocol suite, they are an indispensable part of the Interledger model.

As payments flow between two nodes using the Interledger protocol, their obligations increase and occasionally offset one another. Before the outstanding balance reaches the limit of what the nodes are willing to sustain, they need to settle those balances in some money system they have in common.

For purposes of Interledger, we call all settlement systems ledgers. These can include banks, blockchains, peer-to-peer payment schemes, automated clearing house (ACH), mobile money institutions, central-bank operated real-time gross settlement (RTGS) systems, and even more.
Документация к Rafiki:
https://rafiki.dev/introduction/overview/
https://rafiki.dev/introduction/architecture/
Interledger Connector 
https://github.com/interledgerjs/ilp-connector
Open Payments (API для разработчиков):
https://github.com/interledger/open-payments
Interledger Rafiki:
https://github.com/interledger/rafiki


