# 💻 Préparer la Machine Virtuelle (VM)

Avant de commencer l’installation, nous allons configurer notre machine virtuelle.

---

## 1️⃣ **Créer une Machine Virtuelle**
Ouvrez **VirtualBox** ou **VMware** et créez une nouvelle VM avec ces paramètres :

- **Nom** : `Insérer_votre_nom`
- **Type** : `Linux`
- **Version** : `Arch Linux (64-bit)`
- **Mémoire vive (RAM)** : `4096 MB (4 Go minimum)`
- **Taille du disque dur** : `60 Go`

---

## 2️⃣ **Activer EFI et Virtualisation**
Dans les **paramètres de la VM** :
- **Système** → Activer **EFI**
- **Processeur** → Activer **VT-x/AMD-V**

---

## 3️⃣ **Insérer les ISOs**
Dans **Stockage** :
- **Ajouter l’ISO** de **Arch Linux**
- **Ajouter l’ISO** de **Parrot OS**

---

## 4️⃣ **Lancer la VM**
Démarrez la VM et **choisissez l’ISO Arch Linux** pour commencer l’installation.

**→ Passons à l’installation d’Arch Linux !**  
📌 [Partitionner les disques](pages/arch/partition_disques.md)
