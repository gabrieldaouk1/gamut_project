# 🚀 Installer GRUB

Le bootloader GRUB permet de démarrer votre système Arch Linux et de configurer un dual boot avec Parrot OS.

---

## 📌 **1. Installer GRUB et os-prober**
Installez GRUB et os-prober (nécessaire pour détecter les autres systèmes d’exploitation) :

```bash
pacman -S grub os-prober
```

## 📌 **2. Installer GRUB sur le disque**
Pour installer GRUB dans l’enregistrement de démarrage principal (MBR) ou EFI, utilisez l’une des commandes suivantes selon votre système :

```bash
pacman -S efibootmgr
grub-install --target=x86_64-efi --efi-directory=/boot --bootloader-id=GRUB
```

## 📌 **3. Générer le fichier de configuration GRUB**
Une fois GRUB installé, générez son fichier de configuration pour inclure les systèmes détectés :

```bash
grub-mkconfig -o /boot/grub/grub.cfg
```
---

### 🚀 **Prochaine Étape**
- ✅ **GRUB est prêt à démarrer Arch Linux et Parrot OS.**
- 📌 **On passe à la création d’un utilisateur et à la finalisation du système ?** 🚀
📌 [Créer un utilisateur](pages/arch/creer_utilisateur.md)
