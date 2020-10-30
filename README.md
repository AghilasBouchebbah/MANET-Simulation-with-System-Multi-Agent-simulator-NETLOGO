# MANET-Simulation-with-System-Multi-Agent-simulator-NETLOGO
<br/> **Adaptation du simulateur multi agents Netlogo pour modéliser et simuler un réseau mobile Ad hoc, notamment les deux couches PHY/MAC d’IEEE 802.11**

Résumé

Utilisation d'un simulateur multi agents 'NETLOGO' pour modéliser et simuler les aspects les plus élevés des réseaux mobiles ad hoc (MANETs). J'ai conçus et mis en œuvre un modèle de réseau MANET qui permet de simuler en particulier les principaux protocoles et aspects liés aux deux couches PHY et MAC de la norme IEEE 802.11 utilisées pour les réseaux Ad hoc (transmission radio et contrôle d’accès au canal CSMA/CA DCF), la mobilité des nœuds, ainsi que le mécanisme de routage à court chemin qui assure l’acheminement des paquets dans le réseau.

Mots-clés : NETLOGO, simulation et modélisation, réseau mobile ad hoc (MANET), IEEE 802.11, Transmission radio, CSMA/CA, mobilité, routage.

<br/>

Abstract

use of a 'NETLOGO' multi-agent simulator to model and simulate the highest aspects of mobile ad hoc networks (MANETs). I designed and implemented a MANET network model which makes it possible to simulate in particular the main protocols and aspects related to the two PHY and MAC layers of the IEEE 802.11 standard used for Ad hoc networks (radio transmission and channel access control CSMA / CA DCF ), the mobility of nodes, as well as the short-path routing mechanism that ensures the routing of packets in the network.

Keywords : NETLOGO, modeling and simulating, mobile ad hoc networks (MANET), IEEE 802.11, radio transmission, CSMA/CA, mobility, routing.


<br/>
<br/>
<br/>

<h1> Exemple de simulation  </h1>
<br/>

<h2> ommunication sans le protocole d'accés CSMA/CA </h2>
<br/>

![envoi 2](https://user-images.githubusercontent.com/58481599/97761356-cba05180-1b05-11eb-9c55-88a286a5f85a.PNG)

![envoie 3rep](https://user-images.githubusercontent.com/58481599/97762624-6f3f3100-1b09-11eb-98ca-c9f4d512618b.PNG)

<br/>

![Capture](https://user-images.githubusercontent.com/58481599/97763734-cbf01b00-1b0c-11eb-8925-ab362ee82247.JPG)

<br/> 

**Les ondes**
</br/>
![onde](https://user-images.githubusercontent.com/58481599/97761441-01453a80-1b06-11eb-8679-f180c93ff399.png)

<br/>
<br/>
<h2>Communication avec le protocole d'accés CSMA/CA </h2>
<br/>

![csma-ca final](https://user-images.githubusercontent.com/58481599/97761388-e377d580-1b05-11eb-9562-91cd360e14ae.png)

![netlogo](https://user-images.githubusercontent.com/58481599/97761430-fb4f5980-1b05-11eb-8fac-abb93c7b1184.PNG)

<br/>

![Capture2](https://user-images.githubusercontent.com/58481599/97763776-f510ab80-1b0c-11eb-8a95-65f750bf6998.JPG)

<br/> 

<br/>
<br/>

<h3> Les paramètres d’entrés : <h3/>
  
  <br/>
  
 **Nombre_noeuds** : un slider qui permet à l’utilisateur d’entrer le nombre de noeuds de ce réseaux.
 
 <br/>
 
 **Rayon_transmission** : l’utilisateur indique la valeur du rayon de transmission, le cercle de la portée prendra comme taille cette valeur, et des liens seront créés      
 avec les noeuds voisin qui se trouve à l’intérieur de cette étendu.
 
 <br/>
 
 **Visualise_portée** : activer ou désactiver la visualisation du cercle de la portée des noeuds, dans ce cas de figure, il est désactivé.
 
 <br/>
 
 **CWmin et CWmax** : l’utilisateur entre la valeur de l’intervalle de la fenêtre de contention.
 
 <br/>
 
 **Nombre_tentative** : l’utilisateur indique la valeur de nombre de tentative de retransmission d’un paquet avant qu’il soit détruit.
 
 <br/>
 
 **PER**: le taux d'erreur de paquet (PER) est le nombre de paquets de données incorrectement reçus divisé par le nombre total de paquets reçus. ce taux inclue BER (bits    error rate), bruit thermique, Multipath et Fading.
Pour calculer la probabilité d'erreur, on utilise les entrées Base et PER pour indiquer le taux de probalité d’erreur. Par exemple, pour avoir un taux = 0,035, il faut définir le PER sur 3,5 et la base à 1.0E-2 = 0.01.

<br/>
<br/>

<h3>Les boutons :</h3>

<br/>

**Chaque bouton, une procédure écrite dans la partie code lui est affecté. L’exécution de ces procédures désigne les actions des agents.**

<br/>

 **Setup** : le bouton qui exécute la procédure To Setup, et qui permet de créer les agents, initialiser les variable, créer les liaisons entre les noeuds voisins,

<br/>

**Moblité** : exécuté en boucle : les noeuds se déplace dans l’envirenement d’une manière aléatoire, par conséquent, la topologie du réseau est en changement continue,    les liens disparaissent, et d’autres se créent, selon la portée radio de chaque noeud.

<br/>

**Generer et envoyer** : concernent un envoie de message simple, c-a-d : un seul noeud génère un message et le transmit au noeud destinataire, soit à un saut unique,      soit à sauts multiples (en exécutant l’algorithme de routage).

<br/>

**Generer_message et csmaCa_dcf** : dans ce cas de simulation, les deux boutons s’éxecute en boucle. Le premier permet à chaque agent noeud de générer des paquets de      données, ces derniers sont insérés dans le buffer des transmissions.
   Les agents noeuds envoient leurs paquets en exécutant l’algorithme CSMA/CA.
   
   <br/>
   <br/>

<h3> Deroulement : </h3>

<br/>

<p>En appuyant sur le bouton « générer_messages », les noeuds génèrent des messages et créent des entêtes propres aux messages (type de message, identifiant de la source, identifiant de la destination, nombre de sauts, identifiant de noeud relay).
Ensuite, en appuyant sur le bouton « csmaCa_dcf », le protocole CSMA-CA se met à s’exécuter afin gérer les transmissions des messages dans les IBSS. Ce dernier s’exécute en coopération avec le protocole de routage à court chemin implementé.</p>
