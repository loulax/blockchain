# La sécurité dans la blockchain



## Principes de la cryptographie



Transmettre des messages de manière chiffré grâce à des systèmes de codage pour permettre au destinataire qui est censé être le seul à pouvoir déchiffrer et interpréter le message reçu. 

Exemple de système : Code César

Ce dernier consiste à décaler chaque lettre de l'alphabet de 3 rangs vers la droite pour coder et 3 rangs vers la gauche pour décoder

Exemple pour la phrase "Ce message est code" => **FH PHVVDKH HVW FRGH**

Il existe 2 types d'algorithmes de chiffrement:

- Algorithmes à clé publique
- Algorithmes à clé secrète



<u>Le chiffrement symétrique ou "clé privé:"</u>

La personne A possède la clé privé elle envoie le message avec la clé privé à la personne B qui la déchiffre

<u>Le chiffrement asymétrique ou "clé publique":</u>

La personne A récupère la clé publique de la personne B via un serveur de clé puis lui envoi le message

La personne B récupère aussi la clé publique de la personne A pour lui permettre de déchiffrer le message

C'est le système de chiffrement utilisé par la blockchain actuellement.



## Quel lien entre décentralisation et sécurité

Vitalik (Développeur de la blockchain Ethereum) a développé le concept de triangle d'incompatibilité ou trilemme de la blockchain. Cela stipule qu'il n'est pas possible en développant une blockchain de pouvoir optimiser en même temps les 3 principes:

- Sécurité
- Scalabilité
- Décentralisation

<u>Sécurité :</u> Ce principe permet de s'assurer que le réseau puisse prendre en compte toutes les transactions sans que celles-ci ne puissent être modifié et vérifiant leur authenticité de bout en bout et ne prévenant les attaques.

 <u>Décentralisation:</u> Ce principe permet de faire en sorte que la crypto soit autonome et ne dépendent pas d'un point central.

<u>Scalabilité:</u> Les transactions doivent s'adapter suivant la taille du réseau. La vitesse et les frais de transactions ne doivent pas être impacté pour l'utilisateur final quelque soit le nombre de transactions dans le même temps 200 ou 2M de personnes sur le réseau.

![Quelques cryptos du trilemme](img\trilemme_blockchain.png)



## Infrastructure du système distribuée

![Infrastructure d'un système blockchain](img\infra_blockchain.png)

Ces infrastructures connaissent des enjeux de sécurité tels que des attaques de type :

- DOS/DDOS: Denial of Service, le principe de cette attaque est de "flood" la cible en envoyant un nombre de requêtes trop importante pour qu'elle ne puisse plus répondre et impacte l'accès aux utilisateurs.
- MITM : Man in the Middle, ce type d'attaques permet d'usurper l'identité d'un tiers  en se mettant entre 2 équipements. Cette attaque est couramment utilisée dans un réseau lan afin voler des informations par exemple. Exemple : Un pc A souhaite Accéder au site www.facebook.com/,  dans une communication normale, il va directement envoyer les requêtes à son prochain routeur qui lui va relayer les paquets vers le serveur cible qui héberge facebook. Mais dans ce cas un pc X va s'interposer discrètement entre le pc A et le routeur pour "sniffer" les communications et pouvoir y voler ses informations de connexion. C'est totalement transparent car l'attaquant va configurer son système pour permettre de relayer les messages entre le pc A et le routeur. C'est aussi le cas pour du phishing, l'attaquant va créer un site bidon et rediriger les requêtes dns vers son serveur en renvoyant la page que l'utilisateur souhaite. Ce dernier pense être sur le bon site et va saisir ses informations confidentielles sans savoir que celles-ci vont être récupérées en clair.
- IP spoofing: L'attaquant va usurper l'adresse ip pour communiquer avec son destinataire et y récupérer des informations sans que ces derniers ne s'en rende compte
- Reniflement de paquets: L'attaquant va intercepter tout le trafic réseau grâce à des outils tel que Wireshark. Ce dernier est le plus connu et est utilisé pour les attaques ci-dessus.



## La sécurité des blocs

Chaque nouveaux bloc est relié à tous les autres blocs qui le précèdent dans une chaîne cryptographique, ce mécanisme rend la falsification des données très difficile. Toutes les transactions dans les blocs sont validées et approuvées par un mécanisme de consensus.

Le consensus est le terme permettant de désigner la ou les manières de vérifier chaque bloc par des mécanismes tel que le PoW (Proof of Work) utilisé par Bitcoin, il y a aussi le PoS (Proof of Stack) utilisé par Ethereum.

Les principales caractéristiques :

L'identification de chaque partie s'effectue par un procédé cryptographique.

La transaction est envoyé à tous les nœuds qui compose la blockchain en question. Un nœud est un réseau d'ordinateur se trouvant dans le monde entier qui vont effectuer les calculs pour valider les transactions. Chaque nœuds garde une copie dans un registre des transactions traitées.

Le système de sécurisation utilisant le consensus pour valider chaque bloc afin de les rendre fiables.



### Chiffrement et hashage

L'implémentation peux différer selon la blockchain mais les principaux éléments dans un bloc sont les suivants:

- Index
- Hash servant à identifier le bloc
- Hash du bloc précédent
- Timestamp
- Les transactions

Le 1er bloc d'une blockchain est appelé le <u>**Genesis block**</u>

![Les différents éléments d'un bloc](C:\Users\loulax\Documents\Blockchain\img\block_datas.png)



Le site suivant permet de voir comment tout cela fonctionne : https://andersbrownworth.com/blockchain/blockchain

**Il faut savoir que si une information venait à changer sur l'un des blocs, il faudra que les tous les blocs suivants recalcule leur hash pour valider le consensus et ainsi uniformiser l'ensemble de la blockchain.**