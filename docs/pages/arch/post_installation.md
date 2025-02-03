# 🛠 Post-installation et configuration de l'environnement KDE

Maintenant que le système est installé et fonctionnel, nous allons ajouter des outils essentiels et un environnement graphique **KDE Plasma**.

---

## 📌 **1. Mettre à jour le système**
Avant d’installer de nouveaux paquets, mettez à jour Arch Linux :

```bash
sudo pacman -Syu
```

## 📌 **2. Configurer la locale (langue du système)**
Par défaut, Arch Linux ne définit pas la langue du système. Nous allons activer **l’anglais UTF-8**.  
1️⃣ **Ouvrez le fichier de configuration des locales** :

```bash
sudo nano /etc/locale.gen
```

2️⃣ Décommentez la ligne suivante (supprimez le #) pour activer en_US.UTF-8 :

```bash
en_US.UTF-8 UTF-8
```

3️⃣ Générez la locale :

```bash
 sudo locale-gen
```

## 📌 **3. Installer NetworkManager**
Si NetworkManager n’a pas été installé précédemment, installez-le et activez-le :
```bash
sudo pacman -S networkmanager
sudo systemctl enable NetworkManager
sudo systemctl start NetworkManager
```

## 📌 **4. Installer l'environnement graphique KDE Plasma**
1️⃣Installez KDE Plasma et les paquets essentiels :
```bash
sudo pacman -S plasma kde-applications
```

2️⃣Activez le gestionnaire de session SDDM (utilisé par KDE) :
```bash
sudo systemctl enable sddm
sudo systemctl start sddm
```

---

### 🚀 **Prochaine Étape**
- ✅ **Arch Linux est maintenant prêt avec KDE Plasma et les outils essentiels.**
📌 [Parrot os](pages/arch/creer_utilisateur.md)
