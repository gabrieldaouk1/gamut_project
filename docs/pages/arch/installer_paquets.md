# 📦 Installer les paquets système

Nous allons maintenant installer le système de base d’Arch Linux, ainsi que les paquets nécessaires pour démarrer et configurer le système.

---

## 📌 **1. Installer les paquets essentiels**
Lancez la commande suivante pour installer tous les paquets nécessaires :

```bash
pacstrap /mnt linux linux-firmware base base-devel vim nano emacs lvm2 grub os-prober efibootmgr dosfstools mtools networkmanager
```

### **Explications des paquets installés :**

- **`linux`** : Installe le noyau Linux.  
- **`linux-firmware`** : Contient les firmwares nécessaires pour le matériel.  
- **`base`** : Ensemble de paquets essentiels pour Arch Linux.  
- **`base-devel`** : Outils de développement de base (comme `make`, `gcc`...).  
- **`vim`, `nano`, `emacs`** : Éditeurs de texte (choisissez celui que vous préférez).  
- **`lvm2`** : Nécessaire pour gérer les volumes logiques.  
- **`grub`** : Bootloader pour charger Arch Linux au démarrage.  
- **`os-prober`** : Détecte automatiquement les autres OS pour le dual boot.  
- **`efibootmgr`** : Utilitaire pour gérer les entrées de boot EFI.  
- **`dosfstools`, `mtools`** : Outils pour gérer les partitions FAT32 (nécessaire pour EFI boot).  
- **`networkmanager`** : Permet de gérer la connexion réseau après installation.  


## 📌 **2. Générer le fichier fstab**
Une fois les paquets installés, générez le fichier fstab (table de montage) pour que le système sache comment monter les partitions au démarrage.

```bash
genfstab -U /mnt >> /mnt/etc/fstab
```

Pour s'assurer qu'il est correct, affichez son contenu :
````bash
cat /mnt/etc/fstab
````

---

### 🚀 **Prochaine Étape**
✅ **Les paquets système sont bien installés !**  
📌 **On passe à la configuration du noyau et des volumes logiques ?** 🚀
📌 [Accéder au système](pages/arch/arch_chroot.md)
