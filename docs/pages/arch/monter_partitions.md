# 📂 Monter les partitions

Maintenant que les partitions sont formatées, nous allons les **monter dans le système de fichiers** pour permettre l’installation d’Arch Linux.

---

## 📌 **1. Monter la partition root d’Arch Linux**
Nous devons d’abord monter la partition **root** (`/`) dans `/mnt`.

```bash
mount /dev/vg_arch/root /mnt
```

## 📌 **2. Monter les partitions secondaires**
Une fois la racine montée, nous créons les répertoires nécessaires et montons les partitions suivantes :
```bash
mkdir /mnt/boot
mount /dev/sda1 /mnt/boot

mkdir /mnt/home
mount /dev/vg_arch/home /mnt/home
```

Activez également le swap : 
```bash
swapon /dev/vg_arch/swap
```

## 📌 **2. Monter les partitions secondaires**
Pour s’assurer que tout est bien monté, utilisez la commande suivante 
```bash
lsblk
```

Vous devriez voir une sortie similaire à ceci: 
```bash
NAME                MAJ:MIN RM  SIZE RO TYPE MOUNTPOINT
sda                   8:0    0   60G  0 disk  
├─sda1                8:1    0  400M  0 part /mnt/boot  
├─sda2                8:2    0   21G  0 part  
│  ├─vg_arch-root   254:0    0   15G  0 lvm  /mnt
│  ├─vg_arch-home   254:1    0    5G  0 lvm  /mnt/home
│  └─vg_arch-swap   254:2    0  500M  0 lvm  [SWAP]
```
---

### 🚀 **Prochaine Étape**
✅ **Formatage et swap configurés avec succès !**  
📌 **On enchaîne avec le montage des partitions ?** 🚀
📌 [Installer avec l'installationd des paquets](pages/arch/monter_partitions.md)
