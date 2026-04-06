# Transport Pro — Guide de déploiement Vercel

## Structure des fichiers à uploader sur GitHub

```
transport-app/
├── dashboard.html      ← Votre tableau de bord
├── chauffeur.html      ← Interface chauffeur
└── vercel.json         ← Configuration des routes
```

## Contenu du fichier vercel.json

Créez un fichier `vercel.json` avec ce contenu exactement :

```json
{
  "rewrites": [
    { "source": "/dashboard", "destination": "/dashboard.html" },
    { "source": "/chauffeur", "destination": "/chauffeur.html" }
  ]
}
```

## Étapes de déploiement

### 1. Créer le dépôt GitHub
1. Allez sur github.com → New repository
2. Nommez-le `transport-app`
3. Cochez "Public"
4. Cliquez "Create repository"
5. Uploadez les 3 fichiers : dashboard.html, chauffeur.html, vercel.json

### 2. Déployer sur Vercel
1. Allez sur vercel.com → New Project
2. Cliquez "Import" sur votre repo transport-app
3. Framework Preset : "Other"
4. Cliquez Deploy
5. Attendez 1-2 minutes → votre site est en ligne !

### 3. Vos URLs
Une fois déployé, Vercel vous donne une URL comme :
`https://transport-app-xxxx.vercel.app`

- Dashboard (vous) : `https://transport-app-xxxx.vercel.app/dashboard.html`
- Chauffeur Camion 01 : `https://transport-app-xxxx.vercel.app/chauffeur.html?camion=01`
- Chauffeur Camion 02 : `https://transport-app-xxxx.vercel.app/chauffeur.html?camion=02`
- Chauffeur Camion 03 : `https://transport-app-xxxx.vercel.app/chauffeur.html?camion=03`

### 4. Générer les QR codes
Dans le dashboard → page Camions → cliquez "QR code" sur chaque camion.
Un vrai QR code apparaît. Cliquez "Imprimer" pour l'imprimer directement.

### 5. Tester
1. Ouvrez `chauffeur.html?camion=01` sur votre téléphone
2. Prenez une photo
3. Envoyez
4. Ouvrez le dashboard → vous voyez la notification apparaître

## Domaine personnalisé (optionnel)
Dans Vercel → Settings → Domains → ajoutez votre propre domaine
Ex: transport.monentreprise.com
