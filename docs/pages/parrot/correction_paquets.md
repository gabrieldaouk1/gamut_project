# 🛠️ Correction des erreurs de paquets (optionnel)

Cette étape n’est pas obligatoire mais **recommandée** si vous rencontrez des erreurs lors de `sudo apt install` ou `sudo apt update` dans Parrot OS.

---

## 📌 **1. Mettre à jour les paquets**
Avant toute correction, commencez par mettre à jour la liste des paquets :

```bash
sudo apt update
```

## 📌 **2. Régénérer la clé d’archive de Parrot OS**
Si vous rencontrez une erreur liée aux clés GPG (The following signatures couldn't be verified), réinstallez parrot-archive-keyring :

```bash
sudo wget https://deb.parrot.sh/parrot/pool/main/p/parrot-archive-keyring/parrot-archive-keyring_2024.12_all.deb
sudo dpkg -i parrot-archive-keyring_2024.12_all.deb
```

## 📌 **3. Mettre à jour complètement le système**
Après la correction des clés GPG, mettez à jour tous les paquets :
```bash
sudo apt upgrade
```


---

### 🚀 **Résumé**
- **Mise à jour et correction des clés d’archives** de Parrot OS.
- **Aucune erreur de paquets** après cette correction.

📌 **On passe à la configuration du serveur Web ?** 🚀
📌 [Installer un serveur SSH](pages/serveurs/installer_ssh)