# 🐘 Installer PHP et configurer PHP-FPM pour Nginx

PHP est un langage de programmation utilisé pour le développement web dynamique. Nous allons installer PHP et PHP-FPM pour qu'il fonctionne avec Nginx et MariaDB.

---

## 📌 **1. Installer PHP et PHP-FPM**
Installez **PHP-FPM** et les extensions nécessaires :

```bash
sudo apt install php-fpm -y
```

## 📌 **2. Démarrer et activer PHP-FPM**
1️⃣ Démarrer PHP-FPM :
```bash
sudo systemctl start php8.2-fpm
```

2️⃣ Activer PHP-FPM au démarrage :
```bash
sudo systemctl enable php8.2-fpm
```

3️⃣ Vérifier l’état du service :
```bash
sudo systemctl status php8.2-fpm
```

## 📌 **3. Activer PHP-FPM dans Nginx**
1️⃣ Ouvrez le fichier de configuration de Nginx :

```bash
sudo nano /etc/nginx/sites-available/default
```
2️⃣ Ajoutez ou modifiez les lignes suivantes dans le bloc server {} :
```bash
location ~ \.php$ {
    include snippets/fastcgi-php.conf;
    include fastcgi_params;
    fastcgi_param SCRIPT_FILENAME $document_root$fastcgi_script_name;
    fastcgi_pass unix:/run/php/php8.2-fpm.sock;
}

location ~ /\.ht {
    deny all;
}
```

## 📌 **4. Vérifier et redémarrer les services**
1️⃣ Vérifier la configuration de Nginx :

```bash
sudo nginx -t
```

2️⃣ Redémarrer Nginx et PHP-FPM :
```bash
sudo systemctl restart nginx
sudo systemctl restart php8.2-fpm
```


---

### 🚀 **Résumé**
- **PHP-FPM est installé et fonctionne avec Nginx.**
- **Les fichiers `.php` sont bien interprétés.**

📌 **On continue avec la configuration des sites web maintenant ?** 🚀
📌 [Créer des sites web ](pages/parrot/configurer_sites.md)
