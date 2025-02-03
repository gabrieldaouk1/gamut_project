# ⚙️ Configurer le dual boot avec GRUB

Une fois Arch Linux et Parrot OS installés, nous devons configurer **GRUB** pour détecter les deux systèmes et permettre le choix au démarrage.

---

## 📌 **1. Mettre à jour les paquets nécessaires**
Assurez-vous que **GRUB** et **os-prober** sont bien installés dans Arch Linux :

```bash
sudo pacman -S grub os-prober
```

## 📌 ** 2. Activer os-prober**
Par défaut, GRUB ne détecte pas les autres systèmes si os-prober est désactivé. Vérifions et activons-le :  
1️⃣ Ouvrez le fichier de configuration GRUB :

```bash
sudo nano /etc/default/grub
```
2️⃣ Ajoutez ou modifiez la ligne suivante pour activer os-prober :
```bash
GRUB_DISABLE_OS_PROBER=false
```
3️⃣ Sauvegardez et quittez l’éditeur.

## 📌 ** 3. Générer le fichier de configuration GRUB**
Une fois os-prober activé, générez le fichier de configuration de GRUB pour inclure Parrot OS :
```bash
sudo grub-mkconfig -o /boot/grub/grub.cfg
```


## 📌 **5. Tester le dual boot**
1️⃣ Redémarrez votre machine :
```bash
reboot
```
2️⃣ Au démarrage, vous devriez voir le menu GRUB avec les entrées pour Arch Linux et Parrot OS.  
3️⃣ Sélectionnez Parrot OS et assurez-vous qu’il démarre correctement.


---

### 🚀 **Résumé**
- Le fichier GRUB a été généré pour inclure Parrot OS.
- Vous pouvez maintenant choisir entre Arch Linux et Parrot OS au démarrage.

📌 **On passe à la post-configuration pour optimiser les deux systèmes ?** 🚀
📌 [Accéder au /home de Parrot](pages/parrot/mount_home.md)
