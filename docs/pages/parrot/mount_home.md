# 🗂️ Accéder à `/home` de Parrot OS depuis Arch Linux

Cette section explique comment accéder au répertoire **/home** de Parrot OS directement depuis Arch Linux.

---

## 📌 **1. Créer les points de montage**
Démarrez sur Arch Linux, puis créez les répertoires nécessaires pour monter **/home** de Parrot OS :

```bash
sudo mkdir -p /mnt/parrot
sudo mkdir -p /mnt/parrot/home
```

## 📌 **2. Monter la partition /home**
Montez la partition /home de Parrot OS sur le point de montage :
```bash
sudo mount /dev/vg_parrot/home /mnt/parrot/home
```

## 📌 **3. Ajouter la configuration au fichier fstab**
Pour rendre le montage persistant après chaque redémarrage, ajoutez une entrée dans fstab :  

1️⃣ Ouvrez le fichier fstab avec un éditeur de texte :```bash
```bash
sudo nano /etc/fstab
```
2️⃣ Ajoutez la ligne suivante au fichier, en remplaçant <UUID_de_la_partition> par l’UUID exact de la partition /home de Parrot OS :
```bash
UUID=<UUID_de_la_partition>  /mnt/parrot/home  ext4  rw,relatime  0  2
```

## 📌 **4. Trouver l'UUID de la partition**
Pour trouver l’UUID de la partition, utilisez la commande suivante :
```bash
lsblk -o NAME,UUID,MOUNTPOINT
```

## 📌 **5. Tester le montage et redémarrer**
1️⃣ Une fois que la ligne est ajoutée dans fstab, redémarrez votre machine et boot sur Arch pour tester :  
```bash
reboot
```
2️⃣ Après le redémarrage, vérifiez que la partition est correctement montée : 
 ```bash
ls /mnt/parrot/home
```
---

### 🚀 **Résumé**
- Les partitions nécessaires ont été montées, et le fichier fstab a été mis à jour pour rendre le montage persistant.
- Vous pouvez désormais accéder au répertoire /home de Parrot OS directement depuis Arch Linux.

📌 **On passe à l'optimisation des paquets parrot ?** 🚀
📌 [Correction des erreurs de paquets](pages/parrot/correction_paquets.md)