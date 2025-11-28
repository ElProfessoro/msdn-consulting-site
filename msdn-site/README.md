# MSDN Consulting - Site Vitrine

Site web professionnel optimisé pour MSDN Consulting, prêt à être hébergé sur votre Freebox.

## 📁 Structure du site

```
msdn-site/
├── index.html          # Page d'accueil
├── expertises.html     # Page des expertises
├── clients.html        # Page des références clients
├── contact.html        # Page de contact
├── css/
│   └── style.css      # Feuille de style principale
├── js/
│   └── script.js      # JavaScript (menu mobile, animations)
└── images/            # Tous les logos et icônes
```

## 🚀 Installation sur Freebox

### Étape 1 : Activer l'hébergement Free

1. Connectez-vous à votre **Espace Abonné Free** : https://subscribe.free.fr/login/
2. Allez dans **"Mes services"** → **"Activer mon espace perso"**
3. Notez vos identifiants FTP qui s'afficheront

### Étape 2 : Configurer le client FTP

**Option A - FileZilla (recommandé)**
1. Téléchargez FileZilla : https://filezilla-project.org/
2. Créez une nouvelle connexion :
   - Hôte : `ftpperso.free.fr`
   - Identifiant : Votre login Free
   - Mot de passe : Votre mot de passe Free
   - Port : `21`

**Option B - Ligne de commande**
```bash
ftp ftpperso.free.fr
# Entrez votre login et mot de passe
```

### Étape 3 : Upload des fichiers

1. **Avec FileZilla** :
   - Connectez-vous via FTP
   - Dans le panneau de gauche, naviguez vers le dossier `msdn-site`
   - Dans le panneau de droite, vous êtes dans votre espace Free
   - Sélectionnez TOUS les fichiers du site (index.html, expertises.html, etc.)
   - Glissez-déposez les fichiers vers la droite
   - ⚠️ Conservez la structure des dossiers (css/, js/, images/)

2. **En ligne de commande** :
```bash
cd msdn-site
ftp ftpperso.free.fr
> mput *.html
> mkdir css
> cd css
> lcd css
> mput *
> cd ..
> mkdir js
> cd js
> lcd ../js
> mput *
> cd ..
> mkdir images
> cd images
> lcd ../images
> mput *
> bye
```

### Étape 4 : Configurer votre nom de domaine

#### Si vous avez une IP fixe :
1. Dans l'interface de votre registrar (où vous avez acheté le domaine)
2. Configurez un enregistrement DNS de type **A** :
   ```
   Type: A
   Nom: @ (ou www)
   Valeur: [Votre IP Freebox]
   ```
3. Trouvez votre IP Freebox : https://www.free.fr/assistance/

#### Si vous avez une IP dynamique :
1. Utilisez un service DynDNS (gratuit avec Free)
2. Dans votre Espace Abonné Free :
   - **"Mes services"** → **"DynDNS"**
   - Activez le service et notez votre sous-domaine (ex: `votrelogin.freeboxos.fr`)
3. Dans votre registrar, créez un enregistrement **CNAME** :
   ```
   Type: CNAME
   Nom: @ (ou www)
   Valeur: votrelogin.freeboxos.fr
   ```

### Étape 5 : Configuration HTTPS (optionnel mais recommandé)

Pour sécuriser votre site avec HTTPS :

1. **Avec Cloudflare (gratuit)** :
   - Créez un compte sur https://cloudflare.com
   - Ajoutez votre domaine
   - Changez les DNS de votre domaine vers ceux de Cloudflare
   - Activez SSL/TLS (mode "Flexible")
   - Certificat gratuit automatique

2. **Avec Let's Encrypt** (plus technique) :
   - Nécessite un accès SSH à votre Freebox
   - Installation de Certbot
   - Configuration du certificat

## 🎨 Caractéristiques du site

✅ **Design moderne et professionnel**
- Interface épurée avec les couleurs de votre charte (bleu #0B3B7A)
- Typographie Inter pour une lisibilité optimale
- Animations douces au scroll

✅ **Responsive (mobile-friendly)**
- S'adapte automatiquement aux smartphones, tablettes et desktop
- Menu hamburger sur mobile
- Images optimisées

✅ **Performance optimisée**
- CSS minimaliste (~12KB)
- JavaScript léger (~3KB)
- Images compressées
- Temps de chargement < 1 seconde

✅ **SEO-friendly**
- Balises meta correctes
- Structure HTML sémantique
- URLs propres

## 📝 Personnalisation

### Modifier les textes
Éditez directement les fichiers `.html` avec n'importe quel éditeur de texte.

### Changer les couleurs
Dans `css/style.css`, modifiez les variables au début du fichier :
```css
:root {
    --primary-color: #0B3B7A;  /* Votre couleur principale */
    --text-color: #2D3339;     /* Couleur du texte */
    /* etc. */
}
```

### Remplacer les images
Remplacez les fichiers dans le dossier `images/` en gardant les mêmes noms.

### Activer le formulaire de contact
Le formulaire actuel affiche un simple message. Pour le rendre fonctionnel :
- Utilisez un service comme **Formspree** (gratuit)
- Ou configurez un script PHP sur votre Freebox

## 📊 Statistiques du site

- **Poids total** : ~600 KB
- **Pages** : 4 (Accueil, Expertises, Clients, Contact)
- **Images** : 16 logos/icônes optimisés
- **Compatible** : Tous navigateurs modernes

## 🔧 Support & Maintenance

Le site est entièrement statique (HTML/CSS/JS), donc :
- ✅ Aucune base de données requise
- ✅ Aucune mise à jour de sécurité
- ✅ Très faible consommation de ressources
- ✅ Parfait pour 10 visiteurs/jour

## 🌐 URLs du site

Une fois en ligne, votre site sera accessible à :
- `http://votre-domaine.com` (ou .fr, etc.)
- `http://votrelogin.free.fr` (URL Free par défaut)

## 📞 Besoin d'aide ?

Si vous rencontrez des problèmes :
1. Vérifiez que tous les fichiers sont bien uploadés
2. Vérifiez la structure des dossiers (css/, js/, images/)
3. Consultez l'aide Free : https://www.free.fr/assistance/
4. Vérifiez les permissions des fichiers (644 pour les .html, .css, .js)

---

🎉 **Félicitations !** Votre site est prêt à être mis en ligne sur votre Freebox.
