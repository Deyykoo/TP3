# TP3
## 1. Echange ARP
```
🌞Générer des requêtes ARP

  commande = ip neigh show & ip a
- ping 10.3.1.11  
- ping 10.3.1.12  
- 10.3.1.11 dev enp0s3 lladdr 08:00:27:09:08:b6 < adresse mac  
  10.3.1.12 dev enp0s3 lladdr 08:00:27:93:6a:b3 < adresse mac  
```
## 1. Mise en place du routage
```
🌞Ajouter les routes statiques nécessaires pour que john et marcel puissent se ping  

- sudo ip route add 10.3.1.11/24 via 10.3.1.254 dev enp0s3
- sudo ip route add 10.3.1.12/24 via 10.3.1.254 dev enp0s3 

- Vérification :
De marcel à john :

PING 10.3.1.11 (10.3.1.11) 56(84) bytes of data.
64 bytes from 10.3.1.11: icmp_seq=1 ttl=64 time=1.35 ms
64 bytes from 10.3.1.11: icmp_seq=2 ttl=64 time=1.16 ms
64 bytes from 10.3.1.11: icmp_seq=3 ttl=64 time=1.25 ms

De john à marcel :
PING 10.3.2.12 (10.3.2.12) 56(84) bytes of data.
64 bytes from 10.3.2.12: icmp_seq=1 ttl=64 time=1.19 ms
64 bytes from 10.3.2.12: icmp_seq=2 ttl=64 time=1.16 ms
64 bytes from 10.3.2.12: icmp_seq=3 ttl=64 time=1.35 ms

