# 🎯 TopoCAD Pro v1.0

## Application Professionnelle de Traitement Topographique

TopoCAD Pro transforme vos plans PDF topographiques en modèles 3D exploitables, avec export DXF compatible AutoCAD.

---

## ✨ Fonctionnalités v1.0

### 📥 Import & Extraction Intelligente
- **Drag & Drop** de fichiers PDF
- **Reconnaissance universelle** de 14+ formats d'altitude :
  - `NE = 143.21m`
  - `NGF = 143.21`
  - `Z = 143.21`
  - `Alt: 143.21`
  - `Cote: 143.21`
  - `143.21m`
  - `143,21m` (virgule)
  - Et bien d'autres...
  
- **5 systèmes de coordonnées** supportés :
  - Lambert 93 (France métropolitaine)
  - Lambert II étendu
  - UTM
  - WGS84 (Lat/Lon)
  - Personnalisé

### 🎮 Visualisation 3D Interactive
- Points automatiquement placés à leur **vraie altitude**
- Navigation intuitive :
  - 🖱️ Clic gauche + glisser : Rotation (Orbit)
  - 🖱️ Clic droit + glisser : Déplacement (Pan)
  - 🖱️ Molette : Zoom
- **Exagération verticale** réglable (1x à 10x)
- Grille de référence
- Éclairage professionnel pour relief

### 💾 Export Professionnel
- **Export DXF** avec points 3D (X, Y, Z)
- Format **AutoCAD R12** compatible
- Layers organisés : `POINTS_TOPO`
- **Export CSV** avec toutes les données

### 📊 Statistiques en Temps Réel
- Nombre de points extraits
- Altitude min/max
- Diagnostic détaillé de l'extraction
- Logs en temps réel

---

## 🚀 Déploiement sur GitHub Pages

### Fichiers Nécessaires

Vous avez besoin de **3 fichiers seulement** :

```
votre-repo/
├── topocad-pro.html    ← L'application complète
├── README.md           ← Documentation
└── .nojekyll          ← Important pour GitHub Pages
```

### Étapes de Déploiement

#### 1. Créer un Nouveau Repository

Sur GitHub.com :
1. Cliquez sur **"+"** → **"New repository"**
2. Nom : `topocad-pro` (ou votre choix)
3. Public ✅
4. **Ne pas** initialiser avec README
5. Créer

#### 2. Uploader les Fichiers

**Option A - Interface GitHub (Simple)** :
1. Dans votre nouveau repository, cliquez **"Add file"** → **"Upload files"**
2. Glissez-déposez les 3 fichiers
3. Commit : "Initial commit - TopoCAD Pro v1.0"

**Option B - Git (Terminal)** :
```bash
git init
git add .
git commit -m "TopoCAD Pro v1.0"
git branch -M main
git remote add origin https://github.com/VOTRE_USERNAME/topocad-pro.git
git push -u origin main
```

#### 3. Activer GitHub Pages

1. Dans votre repository, allez dans **Settings**
2. Menu gauche → **Pages**
3. Source :
   - Branch : **main**
   - Folder : **/ (root)**
4. Cliquez **Save**

⏳ **Attendez 2-3 minutes**

✅ **Votre application est en ligne !**
```
https://VOTRE_USERNAME.github.io/topocad-pro/topocad-pro.html
```

---

## 📖 Guide d'Utilisation

### 1. Importer un PDF

**Méthode 1 - Drag & Drop** :
- Glissez votre PDF topographique sur la zone bleue

**Méthode 2 - Bouton** :
- Cliquez sur "Choisir un fichier"
- Sélectionnez votre PDF

### 2. Choisir le Système de Coordonnées

Avant l'import, sélectionnez le système utilisé dans votre PDF :
- **Lambert 93** : France métropolitaine (moderne)
- **Lambert II étendu** : Ancien système français
- **UTM** : Coordonnées universelles
- **WGS84** : Latitude/Longitude
- **Personnalisé** : Pour autres systèmes

### 3. Exploration 3D

Une fois les points extraits :
- **Naviguez** avec la souris (voir contrôles ci-dessous)
- **Ajustez l'exagération** verticale pour mieux voir le relief
- **Activez/désactivez** la grille

### 4. Export

Deux options d'export :

**Export DXF (AutoCAD)** :
- Cliquez "Export DXF"
- Fichier téléchargé automatiquement
- Ouvrez dans AutoCAD, BricsCAD, ou tout logiciel CAO
- Les points sont en 3D avec leur vraie altitude

**Export CSV** :
- Cliquez "Export CSV"
- Format : ID, X, Y, Z, Lambert_X, Lambert_Y, Source
- Ouvrez dans Excel, QGIS, ou autre

---

## 🎓 Contrôles 3D

| Action | Contrôle |
|--------|----------|
| **Rotation** | Clic gauche + glisser |
| **Déplacement** | Clic droit + glisser |
| **Zoom** | Molette de la souris |
| **Reset vue** | Recharger l'import |

---

## 🔍 Diagnostic

Le panneau de diagnostic vous aide à comprendre l'extraction :

- ✅ **Succès** (vert) : Points extraits avec succès
- ⚠️ **Warning** (orange) : Avertissements
- ❌ **Erreur** (rouge) : Problèmes à résoudre

**Exemple de diagnostic** :
```
[14:30:25] 📄 Chargement du PDF...
[14:30:26] ✅ PDF chargé: 1247 éléments de texte trouvés
[14:30:27] 📍 Coordonnées X trouvées: 45
[14:30:27] 📍 Coordonnées Y trouvées: 45
[14:30:27] ✓ NE = XXX.XXm: 23 points
[14:30:27] ✓ XXX.XXm: 15 points
[14:30:27] ✅ 38 points d'altitude extraits
```

---

## 🐛 Résolution de Problèmes

### Problème : Aucun Point Extrait

**Solutions** :
1. Vérifiez que votre PDF contient du **texte sélectionnable** (pas une image scannée)
2. Consultez le **diagnostic** pour voir les formats détectés
3. Essayez un **autre système de coordonnées**
4. Si c'est un scan, utilisez d'abord un logiciel OCR

### Problème : Coordonnées Lambert Non Trouvées

**Solutions** :
1. Vérifiez que votre PDF contient des annotations `X = ...` et `Y = ...`
2. Les points seront quand même extraits, mais avec coordonnées PDF
3. L'export DXF fonctionnera avec les coordonnées disponibles

### Problème : La Vue 3D est Plate

**Solutions** :
1. Augmentez l'**exagération verticale** (curseur dans Paramètres 3D)
2. Vérifiez que les altitudes sont bien extraites (panneau Statistiques)
3. Zoomez plus près du modèle

---

## 💡 Astuces Pro

### 1. Format de PDF Idéal
✅ **Bon** :
- PDF généré par AutoCAD, QGIS, ou logiciel CAO
- Texte sélectionnable
- Coordonnées et altitudes en clair

❌ **Problématique** :
- Scan papier sans OCR
- Altitudes en image
- PDF protégé

### 2. Optimiser l'Extraction
- Utilisez le **bon système de coordonnées**
- Vérifiez le diagnostic pour voir quels patterns fonctionnent
- Si peu de points extraits, le PDF utilise peut-être un format non standard

### 3. Export AutoCAD
- Les points 3D sont sur le layer `POINTS_TOPO`
- La couleur par défaut est le cyan (3)
- Vous pouvez changer le layer, la couleur, etc. dans AutoCAD

---

## 📊 Spécifications Techniques

### Formats Supportés
- **Input** : PDF (avec texte sélectionnable)
- **Output** : DXF R12, CSV

### Limites
- **Points max recommandés** : 10,000 (pour performance optimale)
- **Taille PDF max** : 50 MB
- **Navigateurs** : Chrome, Firefox, Edge, Safari (dernières versions)

### Technologies
- **PDF.js 3.11** : Extraction PDF
- **Three.js r128** : Rendu 3D WebGL
- **Vanilla JavaScript** : Performance optimale
- **Tailwind CSS** : Interface moderne

---

## 🔄 Feuille de Route v1.5 (Prochaine Version)

Fonctionnalités prévues :

- ✅ **Rectangle de sélection** : Sélectionner une zone d'intérêt
- ✅ **Triangulation Delaunay** : Créer un maillage (TIN)
- ✅ **Courbes de niveau** : Générer et exporter
- ✅ **Profils en long** : Tracé et graphique interactif
- ✅ **Export TIN en DXF** : Surfaces 3D
- ✅ **Multi-plans** : Gérer plusieurs PDF

---

## 🆘 Support

### Besoin d'Aide ?

1. **Consultez ce README**
2. **Vérifiez le diagnostic** dans l'application
3. **Créez une Issue** sur GitHub avec :
   - Capture d'écran du diagnostic
   - Format de vos altitudes (ex: "NE = 143.21m")
   - Système de coordonnées utilisé

### Contribuer

Les contributions sont bienvenues !
- 🐛 Signaler des bugs
- 💡 Proposer des améliorations
- 🔧 Soumettre des Pull Requests

---

## 📜 Licence

MIT License - Utilisation libre et gratuite

---

## 🙏 Crédits

Développé pour simplifier le traitement topographique et l'import de plans PDF vers AutoCAD.

**Technologies utilisées** :
- PDF.js par Mozilla
- Three.js par Mr.doob
- Tailwind CSS

---

**Version** : 1.0.0  
**Date** : Novembre 2024  
**Statut** : ✅ Production Ready

**TopoCAD Pro** - Parce que chaque minute compte ! ⏱️🚀
