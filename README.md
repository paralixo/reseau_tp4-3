﻿
Tableau d'adressage

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

Liste du matériel nécessaire :

-   5 serveurs
-   5 imprimantes
-   24 PC (pros, rh, admin)
-   6 switchs
-   36 câbles
-   1 routeur

Utilisation de la topographie en étoile, car on se trouve dans un bâtiment avec un nombre de connexions limités. Par conséquent, il faut mettre le budget sur le switch central car il s'agit d'un point de défaillance important.

Pour la mise en place de l'infrastructure sous GNS3 on à commencé par placer les éléments : " routeur, switchs, PC, imprimante et la NAT ". Pour les PC et les imprimantes on utilise des VPCS car plus facile à configurer et ne consommant pas trop de RAM au lancement. On cable tout et on configure les IP des PC et des imprimantes. On verifie que tout fonctionne en faisant des ping entre PC. Ensuite on configure la NAT ainsi que le routeur. Et on teste en essayant de ping google (8.8.8.8). Au final on finit par configurer les VLAN.

Problématique : Lors de la mise en place de la topographie nous voulions faire une topographie linéaire avec une suite de switch reliés entre eux, mais cette topographique était trop fragile et nous avons préféré la topographie dite en étoile. Cependant même avec cette  topographie cela restait fragile car si le switch du milieu tombe l'infrastructure s'écroule.
