# 🔐 Installer un serveur SSH

L’installation d’un serveur **SSH (Secure Shell)** permet d’accéder à votre machine **à distance** via un terminal sécurisé.

---

## 📌 **1. Installer OpenSSH**
1️⃣Tout d’abord, installez le package **OpenSSH** sur Parrot OS :

```bash
sudo apt install openssh-server -y
```
2️⃣Vérifiez que le service SSH est bien installé :
```bash
systemctl status ssh
```

3️⃣Si le service est inactif, démarrez-le :
```bash
sudo systemctl start ssh
```

4️⃣Pour activer SSH au démarrage :
```bash
sudo systemctl enable ssh
```

5️⃣ Vérifiez que le service SSH est bien installé :
```bash
sudo apt install openssh-server -y
```

## 📌 **2. Configurer le fichier SSH**
1️⃣ Ouvrez le fichier de configuration sshd_config :
```bash
sudo nano /etc/ssh/sshd_config
```

2️⃣ Vérifiez ou modifiez les paramètres suivants pour sécuriser votre serveur SSH :
```bash
# Assurez-vous que SSH écoute sur le bon port (par défaut : 22)
Port 42
```
3️⃣Redémarrez le service SSH pour appliquer les modifications :
```bash
sudo systemctl restart ssh
```
---

### 🚀 **Résumé**
- **Installation et configuration du serveur SSH terminées.**
- **Connexion distante sécurisée possible.**

📌 **On passe à la suite ?** 🚀
📌 [Configurer ssh](pages/serveurs/configurer_ssh)
