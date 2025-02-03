# 🦜 Installer Parrot OS

Nous allons maintenant installer **Parrot OS** en dual boot avec Arch Linux.

---

## 📌 **1. Démarrer l’ISO Parrot OS**
Insérez l’ISO de **Parrot OS** et démarrez votre machine virtuelle ou votre PC physique.  

Dans le menu de démarrage, sélectionnez **"Parrot OS Live"** et appuyez sur **Entrée**.

Une fois arrivé sur le bureau de Parrot OS, lancez l’installation en cliquant sur **"Install Parrot"**.

---

## 📌 **2. Choisir la langue et la disposition du clavier**
1️⃣ Sélectionnez la **langue** de votre système.  
2️⃣ Choisissez votre **disposition de clavier** (exemple : `Français - AZERTY`).  
3️⃣ Cliquez sur **"Suivant"**.

---

## 📌 **3. Configuration du partitionnement**
Puisque nous avons déjà préparé les partitions pour Parrot OS, nous allons **choisir le partitionnement manuel**.

1️⃣ **Sélectionnez** l’option **"Partitionnement manuel"**.  
2️⃣ **Identifiez la partition dédiée à Parrot OS** (`sda4` ou `vg_parrot-root`).  
3️⃣ **Formatez-la en `ext4` et montez-la sur `/`**.  
4️⃣ **Vérifiez que la partition `/boot` existe** (`sda3`, formatée en `vfat`).  
5️⃣ **Vérifiez que le swap est bien détecté** (`vg_parrot-swap`).  
6️⃣ Cliquez sur **"Suivant"** pour valider.

---

## 📌 **4. Installer le système**
L’installateur va maintenant copier les fichiers et installer Parrot OS.  
Patientez jusqu’à la fin du processus.

---

## 📌 **5. Configurer le bootloader**
Si l’installateur demande où installer **GRUB**, sélectionnez **"/dev/sda"**.  
Sinon, nous vérifierons plus tard que **GRUB de Arch Linux** détecte bien Parrot OS.

---

## 📌 **6. Vérification et redémarrage**
Une fois l’installation terminée :
1️⃣ Retirez l’ISO de Parrot OS.  
2️⃣ Cliquez sur **"Redémarrer"**.  
3️⃣ Au redémarrage, **GRUB** doit afficher Arch Linux et Parrot OS.  
4️⃣ Testez le démarrage des deux systèmes.

---

### 🚀 **Prochaine Étape**
✅ **Parrot OS est installé !**  
📌 **Passons à la configuration du dual boot.**  
📌 [Configurer le dual boot](pages/parrot/configurer_dualboot.md)
