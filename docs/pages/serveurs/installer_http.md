# 🌐 Installer un serveur HTTP (Nginx)

Nginx est un serveur web utilisé pour héberger des sites et applications web.

---

## 📌 **1. Installer Nginx**
Installez **Nginx** avec la commande suivante :

```bash
sudo apt install nginx -y
```

## 📌 **2. Démarrer et activer le service**
1️⃣ Démarrer le service Nginx :
```bash
sudo systemctl start nginx
```
2️⃣ Activer le service au démarrage :
```bash
sudo systemctl enable nginx
```
3️⃣ Vérifier que Nginx fonctionne :
```bash
sudo systemctl status nginx
```

## 📌 **3. Tester le serveur Web**
Ouvrir un navigateur et accéder à :
```bash
http://localhost
```
Si la page d’accueil Nginx s’affiche, l’installation est réussie ! ✅


---

### 🚀 **Résumé**
- **Installation de Nginx terminée** et **fonctionnelle**.
- **Le serveur est opérationnel et actif au démarrage**.
- **Vérification via `http://localhost`**.

📌 **On passe à la suite ?** 🚀
📌 [Installer MariaDB](pages/parrot/installer_http.md)
