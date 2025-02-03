# 🖥 Formater les partitions et configurer le swap

Nous allons maintenant **formater les partitions** et **activer le swap**.

---

## 📌 **1. Formater les partitions**
Chaque partition doit être formatée avec **le bon système de fichiers** :
- **Les partitions de boot** doivent être en **FAT32** (UEFI).
- **Les partitions root et home** doivent être en **ext4**.
- **Le swap** doit être activé après avoir été formaté.

Formatez les partitions d’**Arch Linux** :

```bash
mkfs.vfat -F32 /dev/sda1
mkfs.ext4 /dev/vg_arch/root
mkfs.ext4 /dev/vg_arch/home
mkswap /dev/vg_arch/swap
swapon /dev/vg_arch/swap
````

Puis celles de Parrot OS :

```bash
mkfs.vfat -F32 /dev/sda3
mkfs.ext4 /dev/vg_parrot/root
mkfs.ext4 /dev/vg_parrot/home
mkswap /dev/vg_parrot/swap
swapon /dev/vg_parrot/swap
```

## 📌 ** 2. Vérifications**
Après le formatage, il est important de vérifier que toutes les partitions ont bien été créées et que le swap est actif.

```bash
lsblk
```
Vous devriez voir une sortie similaire à ceci:
```bash
NAME                MAJ:MIN RM  SIZE RO TYPE MOUNTPOINT
sda                   8:0    0   60G  0 disk  
├─sda1                8:1    0  400M  0 part /boot  
├─sda2                8:2    0   21G  0 part  
│  ├─vg_arch-root   254:0    0   15G  0 lvm  /
│  ├─vg_arch-home   254:1    0    5G  0 lvm  /home
│  └─vg_arch-swap   254:2    0  500M  0 lvm  [SWAP]
├─sda3                8:3    0  500M  0 part /boot/efi  
└─sda4                8:4    0   32G  0 part  
   ├─vg_parrot-root 254:3    0   25G  0 lvm  
   ├─vg_parrot-home 254:4    0    5G  0 lvm  
   └─vg_parrot-swap 254:5    0  500M  0 lvm  [SWAP]
```


---

### 🚀 **Prochaine Étape**
✅ **Formatage et swap configurés avec succès !**  
📌 **On enchaîne avec le montage des partitions ?** 🚀
📌 [Monter les partitions](pages/arch/monter_partitions.md)
