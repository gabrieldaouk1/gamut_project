# 🌐 Configurer des sites web avec Nginx et PHP

Nous allons maintenant créer et configurer **deux sites web** sur notre serveur Nginx.

---

## 📌 **1. Configurer le premier site : `intra.hogwarts.lan`**
1️⃣ **Créer le fichier de configuration Nginx** :

```bash
sudo nano /etc/nginx/sites-available/intra.hogwarts.lan
```
2️⃣ Ajoutez la configuration suivante :
```bash
server {
    listen 80;
    server_name intra.hogwarts.lan;

    root /var/www/intra.hogwarts.lan;
    index index.html index.php;

    location / {
        try_files $uri $uri/ =404;
    }

    location ~ \.php$ {
        include snippets/fastcgi-php.conf;
        fastcgi_pass unix:/run/php/php-fpm.sock;
        fastcgi_param SCRIPT_FILENAME $document_root$fastcgi_script_name;
        include fastcgi_params;
    }
}
```
3️⃣ Sauvegardez et quittez


## 📌 **2. Configurer le premier site : `intra.hogwarts.lan`**
Répéter les mêmes étapes

## 📌 **3. Activer les sites**
Créer un lien symbolique pour activer chaque site :
```bash
sudo ln -s /etc/nginx/sites-available/intra.hogwarts.lan /etc/nginx/sites-enabled/
sudo ln -s /etc/nginx/sites-available/intra-adm.hogwarts.lan /etc/nginx/sites-enabled/
```


## 📌 **4. Créer les dossiers et fichiers pour les sites**
1️⃣ Créer les dossiers :
```bash
sudo mkdir -p /var/www/intra.hogwarts.lan
sudo mkdir -p /var/www/intra-adm.hogwarts.lan
```

2️⃣ Créer des pages HTML de test :
```bash
echo "<h1>Welcome to the Hogwarts students' intranet</h1>" | sudo tee /var/www/intra.hogwarts.lan/index.html
echo "<h1>Welcome to Hogwarts's ADM intranet</h1>" | sudo tee /var/www/intra-adm.hogwarts.lan/index.html
```

## 📌 **5. Vérifier et redémarrer Nginx**
1️⃣ Tester la configuration de Nginx :
```bash
sudo nginx -t
```

2️⃣ Redémarrer Nginx :
```bash
sudo systemctl restart nginx
```

## 📌 **6. Ajouter les domaines au fichier /etc/hosts**
1️⃣ Ouvrir /etc/hosts :
```bash
sudo nano /etc/hosts
```

2️⃣ Ajoutez ces lignes à la fin du fichier :
```bash
127.0.0.1 intra.hogwarts.lan
127.0.0.1 intra-adm.hogwarts.lan
```

## 📌 **7. Tester l’accès aux sites**
1️⃣ Ouvrir un navigateur et tester les deux sites :  
- http://intra.hogwarts.lan  
- http://intra-adm.hogwarts.lan


---

### 🚀 **Résumé**
- **Les VirtualHosts `intra.hogwarts.lan` et `intra-adm.hogwarts.lan` sont créés**.
- **Les sites sont accessibles via un navigateur**.
- **Tout est prêt pour la gestion des bases de données avec PHPMyAdmin**.

📌 **On continue avec PHPMyAdmin ?** 🚀
📌 [Installer PHPMyAdmin](pages/parrot/installer_phpmyadmin.md)

