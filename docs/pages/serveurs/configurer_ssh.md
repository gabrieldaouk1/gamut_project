# 🔐 Configurer un serveur SSH sécurisé

Cette section explique comment configurer **SSH** pour permettre une connexion sécurisée avec des clés SSH.

---

## 📌 **1. Configurer l'accès SSH**
1️⃣ **Créer le dossier SSH** pour l’utilisateur root :

```bash
sudo mkdir -p /root/.ssh
```
2️⃣ Ajouter une clé SSH publique (remplacez "RENTRER ICI CLE SSH PUB" par votre clé) :
```bash
echo "RENTRER ICI CLE SSH PUB" >> /root/.ssh/authorized_keys
```

3️⃣ Restreindre les permissions pour sécuriser la clé :
```bash
sudo chmod 600 /root/.ssh/authorized_keys
```

4️⃣ Redémarrer le service SSH pour appliquer les changements :
```bash
sudo systemctl restart ssh
```

## 📌 ** 2. Se connecter en SSH avec une clé privée**
Depuis un autre ordinateur, utilisez la commande suivante pour vous connecter :

```bash
ssh -i id_rsa -p 42 root@<ip_host>
```


---

### 🚀 **Résumé**
- **Configuration du serveur SSH terminées.**
- **Connexion distante sécurisée possible.**

📌 **On passe à la suite ?** 🚀
📌 [Installer un serveur HTTP](pages/parrot/installer_http.md)