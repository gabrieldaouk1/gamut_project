# 📦 Configurer LVM (Logical Volume Manager)

Nous allons maintenant **initialiser et configurer les volumes logiques** pour Arch Linux et Parrot OS.

---

## 📌 **1. Initialisation des volumes physiques**
Nous allons transformer les partitions **sda2** et **sda4** en **volumes physiques** pour LVM.

```bash
pvcreate /dev/sda2
pvcreate /dev/sda4
```
Vérifiez que les volumes physiques ont bien été créés :
````bash
pvs
````

## 📌 **2. Création des groupes de volumes**
Chaque système aura son propre groupe de volumes :
- Arch Linux → vg_arch 
- Parrot OS → vg_parrot 

```bash
vgcreate vg_arch /dev/sda2
vgcreate vg_parrot /dev/sda4
```
Vérifiez la création des groupes:

````bash
vgs
````

## 📌 **3. Création des volumes logiques**
Chaque système doit contenir :

- Un volume root (/)
- Un volume home (/home)
- Un volume swap (swap)

Création des volumes pour Arch Linux :
````bash
lvcreate -L 15G vg_arch -n root
lvcreate -L 5G vg_arch -n home
lvcreate -L 500M vg_arch -n swap
````

Création des volumes pour Parrot OS :
````bash
lvcreate -L 25G vg_parrot -n root
lvcreate -L 5G vg_parrot -n home
lvcreate -L 500M vg_parrot -n swap
````

Vérifiez la liste des volumes logiques créés :

````bash
lvs
````

## 📌 **4. Vérification avec lsblk**
Une fois les LVM configurés, lancez lsblk pour voir la nouvelle structure des partitions :
````bash
lsblk
````
Vous devriez voir une sortie similaire à ceci
````bash
NAME                MAJ:MIN RM  SIZE RO TYPE MOUNTPOINT
sda                   8:0    0   60G  0 disk  
├─sda1                8:1    0  400M  0 part  
├─sda2                8:2    0   21G  0 part  
│  ├─vg_arch-root   254:0    0   15G  0 lvm  
│  ├─vg_arch-home   254:1    0    5G  0 lvm  
│  └─vg_arch-swap   254:2    0  500M  0 lvm  
├─sda3                8:3    0  500M  0 part  
└─sda4                8:4    0   32G  0 part  
   ├─vg_parrot-root 254:3    0   25G  0 lvm  
   ├─vg_parrot-home 254:4    0    5G  0 lvm  
   └─vg_parrot-swap 254:5    0  500M  0 lvm  
````

Cette sortie montre que :

- Les partitions sda2 et sda4 sont bien utilisées par LVM.
- Les volumes logiques sont bien créés.
Si la sortie ne correspond pas, revérifiez votre configuration LVM.


---

### 🚀 **Prochaine Étape**
✅ **LVM est maintenant bien configuré !**  
📌 **On passe au formatage et au swap ?** 🚀
📌 [Formater et configurer le swap](pages/arch/formater_swap.md)

