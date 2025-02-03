# ⚙️ Configurer le noyau et LVM

Nous allons maintenant configurer le noyau et les volumes logiques pour qu'ils soient fonctionnels après le redémarrage.

---

## 📌 **1. Vérification de LVM**
Assurez-vous que LVM est activé pour permettre la gestion des volumes logiques après le redémarrage.

```bash
lsblk
vgscan
vgchange -ay
```

## 📌 **2. Configurer le noyau avec initramfs**
Générez une nouvelle image initramfs pour inclure le support de LVM.

```bash
mkinitcpio - P
```

## 📌 ** 3. Modifier le fichier mkinitcpio.conf**
Assurez-vous que le hook lvm2 est présent dans le fichier /etc/mkinitcpio.conf :

```bash
nano /etc/mkinitcpio.conf
```
Vérifiez que la ligne suivante est incluse dans la section HOOKS :
```bash
HOOKS=(base udev autodetect modconf block filesystems keyboard fsck lvm2)
```

## 📌 ** 4. Générer une nouvelle image**
Après avoir ajouté ou vérifié le hook lvm2, régénérez l'image initramfs :

```bash
mkinitcpio -P
```

---

### 🚀 **Prochaine Étape**
- ✅ **Noyau et volumes logiques configurés.**
- 📌 **On continue avec l’installation de GRUB ?** 🚀
📌 [Installation de GRUB](pages/arch/installer_grub.md)
