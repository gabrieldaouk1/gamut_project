# 💾 Partitionner les disques

L’objectif est de créer les partitions nécessaires pour installer **Arch Linux et Parrot OS** en **dual boot**.

---

## 📌 **1. Démarrer sur l’ISO Arch Linux**
Une fois l’ISO Arch Linux démarré, ouvrez un terminal et assurez-vous que le clavier est en **français** :

```bash
loadkeys fr
```

## 📌 **2. Création des partitions**
Le disque sera divisé en quatre partitions :  

- Une partition de **400 Mo** pour le boot d'Arch Linux.  
- Une partition de **21 Go** pour les volumes logiques d'Arch Linux.  
- Une partition de **500 Mo** pour le boot de Parrot OS.  
- Une partition de **32 Go** pour les volumes logiques de Parrot OS.  

Lancez l’outil de partitionnement :

```bash
fdisk /dev/sda
```
Créez chaque partition en suivant ces étapes dans fdisk :

```bash
Nouvelle partition → n
Partition principale → p
Définir la taille (+400M, +21G, +500M, +32G)
Sauvegarder les modifications et quitter → wq
```
Taper maintenant la commande suivante :

```bash
lsblk
```
Vous devriez voir une structure similaire à ceci: 
```bash
NAME           MAJ:MIN RM  SIZE RO TYPE MOUNTPOINT
sda              8:0    0   60G  0 disk  
├─sda1           8:1    0  400M  0 part  
├─sda2           8:2    0   21G  0 part  
├─sda3           8:3    0  500M  0 part  
└─sda4           8:4    0   32G  0 part  
```


---
### 🚀 **Prochaine Étape**
💡 **Tout est bien structuré maintenant !**  
**→ Passons à l’installation d’Arch Linux !**  
📌 [Partitionner les disques](pages/arch/configurer_lvm)

