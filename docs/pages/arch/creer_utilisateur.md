# 👤 Créer un utilisateur et finaliser le système

Maintenant que le système de base est configuré, nous allons créer un utilisateur non-root, définir un mot de passe, et appliquer les dernières configurations.

---

## 📌 **1. Définir un mot de passe pour l’utilisateur root**
Avant de créer un utilisateur, définissez un mot de passe pour le compte root :

```bash
passwd
```

## 📌 **2. Créer un utilisateur**
Créez un nouvel utilisateur avec les permissions de base :

```bash
useradd -m -G wheel -s /bin/bash <nom_utilisateur>
```
- -m : Crée automatiquement le répertoire personnel de l'utilisateur.
- -G wheel : Ajoute l’utilisateur au groupe wheel (nécessaire pour les privilèges sudo).
- -s /bin/bash : Définit /bin/bash comme shell par défaut pour cet utilisateur.

Définissez un mot de passe pour cet utilisateur :
```bash
passwd <nom_utilisateur>
```

## 📌 **3. Configurer sudo**
Pour permettre à l’utilisateur d’exécuter des commandes avec sudo, modifiez le fichier sudoers :

```bash
EDITOR=nano visudo
```

Dans le fichier qui s’ouvre, décommentez (retirez le #) la ligne suivante :
```bash
%wheel ALL=(ALL) ALL
```

---

### 🚀 **Prochaine Étape**
- ✅ **L’utilisateur et sudo sont configurés.**
- 📌 **On passe à la finalisation et au premier redémarrage du système ?** 🚀
📌 [Finalisation et reboot](pages/arch/finaliser_reboot.md)

