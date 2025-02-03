# 🗄️ Installer un serveur de base de données (MariaDB)

MariaDB est un système de gestion de bases de données relationnelles (SGBD) compatible avec MySQL. Il est utilisé pour stocker et gérer les données des applications web.

---

## 📌 **1. Installer MariaDB**
Installez **MariaDB** avec la commande suivante :

```bash
sudo apt install mariadb-server -y
```

## 📌 **2. Activer et démarrer MariaDB**
1️⃣ Démarrer le service MariaDB :
```bash
sudo systemctl start mariadb
```

2️⃣ Activer MariaDB au démarrage :
```bash
sudo systemctl enable mariadb
```

3️⃣ Vérifier l’état du service :
```bash
sudo systemctl status mariadb
```


## 📌 ** 3. Tester MariaDB**
1️⃣ Se connecter à MariaDB en ligne de commande :
```bash
sudo mysql -u root -p
```

2️⃣ Créer une base de données de test (exemple) :
```bash
CREATE DATABASE testdb;
SHOW DATABASES;
EXIT;
```

---

### 🚀 **Résumé**
- **MariaDB est installé et fonctionne.**
- **Test de connexion et création de base de données réussis.**

📌 **On continue avec PHP ?** 🚀
📌 [Installer PHP](pages/parrot/installer_php.md)

