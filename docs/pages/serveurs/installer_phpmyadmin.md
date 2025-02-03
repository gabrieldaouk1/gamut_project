# 🗄️ Installer et configurer PHPMyAdmin

PHPMyAdmin est une interface web permettant d’administrer **MariaDB** facilement.

---

## 📌 **1. Installer PHPMyAdmin**
Essayez d’abord d’installer PHPMyAdmin avec **apt** :

```bash
sudo apt install phpmyadmin -y
```

## 📌 **2. Configurer Nginx pour PHPMyAdmin**
1️⃣ Ouvrez le fichier de configuration Nginx :
```bash
sudo nano /etc/nginx/sites-available/default
```
2️⃣ Ajoutez cette section dans le bloc server {} :
```bash
location /phpmyadmin {
    root /var/www/html;
    index index.php index.html index.htm;
    location ~ ^/phpmyadmin/(.+\.php)$ {
        try_files $uri =404;
        include fastcgi_params;
        fastcgi_pass unix:/run/php/php-fpm.sock;
        fastcgi_param SCRIPT_FILENAME $document_root$fastcgi_script_name;
    }
}
```
3️⃣ Vérifiez la configuration de Nginx :
```bash
sudo nginx -t
```
4️⃣ Redémarrez Nginx :
```bash
sudo systemctl restart nginx
```

## 📌 **Tester PHPMyAdmin**
1️⃣ Ouvrez votre navigateur et allez à l’URL :
```bash
http://localhost/phpmyadmin
```
2️⃣ Connectez-vous avec MariaDB :

- Utilisateur : root  
- Mot de passe : (celui défini lors de mysql_secure_installation)  
Si l’interface PHPMyAdmin s’affiche, l’installation est réussie ! ✅


---

### 🚀 **Résumé**
- **PHPMyAdmin est installé et accessible sur `http://localhost/phpmyadmin`**.
- **Compatible avec Nginx et MariaDB**.
- **Connexion testée et fonctionnelle**.

