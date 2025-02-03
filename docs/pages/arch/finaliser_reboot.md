# 🔄 Finaliser et redémarrer le système

Nous allons maintenant finaliser la configuration et redémarrer le système pour tester l’installation d’Arch Linux.

---

## 📌 **1. Nettoyer l'environnement chroot**
Avant de quitter l’environnement **chroot**, assurez-vous que tout est propre et prêt pour le redémarrage. Démontez les partitions et désactivez le swap :

```bash
exit
umount -R /mnt
swapoff -a
```

## 📌 **2. Redémarrer le système**
Une fois les partitions démontées, redémarrez votre machine :

```bash
reboot
```

## 📌 **3. Vérifier le démarrage**
Après le redémarrage, vous devriez voir le menu GRUB. Sélectionnez Arch Linux et appuyez sur Entrée.

---

### 🚀 **Prochaine Étape**
- ✅ **Redémarrage et tests réussis.**
- 📌 **On passe à la post-installation pour peaufiner le système ?** 🚀
📌 [Post-Installation et KDE](pages/arch/post_installation.md)

