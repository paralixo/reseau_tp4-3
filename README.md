# TP4 - Infrastructure Small/mMedium office 

## Tableau d'adressage

|            | 10.4.0.0/24 | vlan |
| ---------- | ----------- | ---- |
| serveur1   |  `10.4.0.1` |   20 |
| serveur2   |  `10.4.0.2` |   20 |
| serveur3   |  `10.4.0.3` |   10 |
| serveur4   |  `10.4.0.4` |   10 |
| serveur5   |  `10.4.0.5` |   10 |
| admin1     |  `10.4.0.6` |   10 |
| RH1        |  `10.4.0.7` |   20 |
| RH2        |  `10.4.0.8` |   20 |
| RH3        |  `10.4.0.9` |   20 |
| ---------- | ----------- | ---- |
| client1-1  | `10.4.0.10` |   20 |
| client2-1  | `10.4.0.11` |   20 |
| client3-1  | `10.4.0.12` |   20 |
| client4-1  | `10.4.0.13` |   20 |
| client5-1  | `10.4.0.14` |   20 |
| ---------- | ----------- | ---- |
| client1-2  | `10.4.0.15` |   20 |
| client2-2  | `10.4.0.16` |   20 |
| client3-2  | `10.4.0.17` |   20 |
| client4-2  | `10.4.0.18` |   20 |
| client5-2  | `10.4.0.19` |   20 |
| ---------- | ----------- | ---- |
| client1-3  | `10.4.0.20` |   20 |
| client2-3  | `10.4.0.21` |   20 |
| client3-3  | `10.4.0.22` |   20 |
| client4-3  | `10.4.0.23` |   20 |
| client5-3  | `10.4.0.24` |   20 |
| ---------- | ----------- | ---- |
| client1-4  | `10.4.0.25` |   20 |
| client2-4  | `10.4.0.26` |   20 |
| client3-4  | `10.4.0.27` |   20 |
| client4-4  | `10.4.0.28` |   20 |
| client5-4  | `10.4.0.29` |   20 |
| imprimante1| `10.4.0.30` |   20 |
| imprimante2| `10.4.0.31` |   20 |
| imprimante3| `10.4.0.32` |   20 |
| imprimante4| `10.4.0.33` |   20 |
| imprimante5| `10.4.0.34` |   20 |

## Liste du matériel nécessaire :

-   5 serveurs
-   5 imprimantes
-   24 PC (pros, rh, admin)
-   6 switchs
-   36 câbles
-   1 routeur

## Devis : 

- 1 routeeur c3640 pour 150€ (d'après Amazon)
- 36 câble pour 60€ (bas de gamme)
- 24 PC pour 12000€ (bas de gamme)
- 5 imprimantes pour 5000€ (bas de gamme, grosses imprimantes d'entreprise)
- 5 serveurs pour 2600€ (entrée de gamme)
- 6 switchs pour 540€ (bas de gamme, il est conseillé d'au moins prendre un meilleeur switch pour le switch central)

Ce qui fait une estimation de 20 350€ pour du matériel bas de gamme. Pour une infrastructure plus résistante nous vous conseillons d'investir plus (notemment sur les câbles et les switchs).

## Mise en place de l'environnement de travail

Pour la mise en place de l'infrastructure sous GNS3 on a commencé par placer les éléments : " routeur, switchs, PC, imprimantes et la NAT ". Pour les PC et les imprimantes on utilise des VPCS car plus facile à configurer et ne consommant pas trop de RAM au lancement. On câble tout et on configure les IP des PC et des imprimantes. On verifie que tout fonctionne en faisant des ping entre PC. Ensuite on configure la NAT ainsi que le routeur. Et on teste en essayant de ping google (8.8.8.8). Au final on finit par configurer les VLAN.

Problématique : Lors de la mise en place de la topographie nous voulions faire une topographie linéaire avec une suite de switchs reliés entre eux, mais cette topographie était trop fragile et nous avons préféré la topographie dite en étoile. Cependant, même avec cette topographie cela restait fragile car si le switch du milieu tombe l'infrastructure s'écroule.
