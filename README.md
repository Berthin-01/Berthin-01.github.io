# 📧 Configuration EmailJS — Portfolio Ralaivelo Berthin

## ✅ État : Formulaire prêt — Activation en 5 minutes

Le formulaire de contact est **entièrement codé et déployé**.  
Il ne reste qu'à connecter votre Gmail via EmailJS (100% gratuit).

---

## 🚀 Étapes de configuration (une seule fois)

### ÉTAPE 1 — Créer un compte gratuit EmailJS

👉 Allez sur **[https://www.emailjs.com](https://www.emailjs.com)**  
→ Cliquez **Sign Up** → créez un compte avec `ralaiveloberthin@gmail.com`  
→ **Plan gratuit** = 200 emails/mois, aucune carte bancaire requise

---

### ÉTAPE 2 — Connecter votre Gmail

1. Dans le dashboard EmailJS, cliquez **Email Services** → **Add New Service**
2. Choisissez **Gmail**
3. Cliquez **Connect Account** → autorisez avec votre compte Google
4. Nommez le service (ex: `portfolio_gmail`)
5. Cliquez **Create Service** → **copiez le Service ID** (ex: `service_abc123`)

---

### ÉTAPE 3 — Créer un template d'email

1. Cliquez **Email Templates** → **Create New Template**
2. Copiez-collez ce template :

**Subject :**
```
📬 Nouveau message de {{from_name}} – Portfolio
```

**Body :**
```
Bonjour Berthin,

Vous avez reçu un nouveau message depuis votre portfolio !

━━━━━━━━━━━━━━━━━━━━━━━━━━━
👤 Nom        : {{from_name}}
📧 Email      : {{reply_to}}
📌 Sujet      : {{subject}}
━━━━━━━━━━━━━━━━━━━━━━━━━━━

💬 Message :
{{message}}

━━━━━━━━━━━━━━━━━━━━━━━━━━━
Répondez directement à cet email pour contacter la personne.
Portfolio : {{portfolio_url}}
```

3. Dans **To Email** : mettez `ralaiveloberthin@gmail.com`
4. Cliquez **Save** → **copiez le Template ID** (ex: `template_xyz789`)

---

### ÉTAPE 4 — Récupérer votre clé publique

1. Cliquez sur votre nom en haut à droite → **Account**
2. Onglet **API Keys**
3. **Copiez la Public Key** (ex: `AbCdEfGhIjKlMnOp`)

---

### ÉTAPE 5 — Mettre à jour le code (2 fichiers)

#### Fichier 1 : `assets/js/main.js` (lignes ~251-253)

Remplacez les 3 lignes :
```javascript
const EMAILJS_SERVICE_ID  = 'YOUR_SERVICE_ID';   // ← votre Service ID
const EMAILJS_TEMPLATE_ID = 'YOUR_TEMPLATE_ID';  // ← votre Template ID  
const EMAILJS_PUBLIC_KEY  = 'YOUR_PUBLIC_KEY';   // ← votre Public Key
```

Par vos vraies clés, exemple :
```javascript
const EMAILJS_SERVICE_ID  = 'service_abc123';
const EMAILJS_TEMPLATE_ID = 'template_xyz789';
const EMAILJS_PUBLIC_KEY  = 'AbCdEfGhIjKlMnOp';
```

#### Fichier 2 : `index.html` (ligne ~22)

Remplacez :
```javascript
emailjs.init({ publicKey: 'YOUR_PUBLIC_KEY' });
```
Par :
```javascript
emailjs.init({ publicKey: 'AbCdEfGhIjKlMnOp' }); // votre vraie clé
```

---

### ÉTAPE 6 — Déployer les changements

Ouvrez PowerShell dans `D:\Berthin\Portfolio\` et tapez :

```powershell
git add .
git commit -m "config: activation EmailJS"
git push origin main
```

✅ **C'est tout !** En 2 minutes le formulaire est actif.

---

## 🔔 Notifications Gmail

Pour recevoir des notifications push sur votre téléphone :
1. Installez **Gmail** sur votre téléphone
2. Activez les notifications dans les paramètres Gmail
3. Chaque email de recruteur déclenchera une notification instantanée

---

## 📊 Tableau de bord EmailJS

Sur **[app.emailjs.com](https://app.emailjs.com)** vous pouvez voir :
- Tous les emails envoyés
- Le nombre restant ce mois (200/mois gratuit)
- Les statistiques d'utilisation

---

## 🌐 Lien public du portfolio

```
https://berthin-01.github.io
```

---

## 📁 Structure du projet

```
D:\Berthin\Portfolio\
├── index.html              ← Page principale
├── CNAME                   ← Domaine personnalisé (si acheté)
├── README.md               ← Ce guide
└── assets/
    ├── css/style.css       ← Styles
    ├── js/main.js          ← JavaScript (EmailJS ici)
    └── images/
        └── IMG_3374.jpg    ← Votre photo de profil
```
