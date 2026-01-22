# GitHub Repository Setup

Instructions pour configurer le dépôt `dvs-community` sur GitHub.

## 1. Créer le dépôt

```bash
# Via GitHub CLI
gh repo create BCISOFT/dvs-community --public --description "Community hub for DevSpaces - Bug reports, feature requests, and discussions"
```

Ou via l'interface GitHub :
- New repository → `dvs-community`
- Public
- Ne pas initialiser avec README (on push les fichiers)

## 2. Pousser les fichiers

```bash
cd dvs-community
git init
git add .
git commit -m "Initial community repository setup"
git remote add origin git@github.com:BCISOFT/dvs-community.git
git push -u origin main
```

## 3. Paramètres du dépôt (Settings)

### General
- [x] Issues enabled
- [x] Discussions enabled
- [ ] Projects (optional)
- [ ] Wiki (désactivé - utiliser docs.devspaces.cloud)

### Features
- Template repository: No
- Sponsorships: Optional

## 4. Activer les Discussions

Settings → Features → Discussions → Enable

### Catégories de Discussions recommandées

| Category | Format | Description |
|----------|--------|-------------|
| 📣 Announcements | Announcement | Updates from the DevSpaces team |
| 💡 Ideas | Open | Share ideas for new features |
| 🙏 Q&A | Question/Answer | Ask the community for help |
| 🙌 Show and Tell | Open | Share your DevSpaces setup |
| 💬 General | Open | Chat about anything |

Pour créer les catégories :
1. Settings → Discussions → Categories
2. Créer chaque catégorie avec le format approprié

## 5. Importer les Labels

Les labels sont définis dans `.github/labels.yml`.

### Option A : GitHub CLI (recommandé)

```bash
# Supprimer les labels par défaut
gh label list --json name --jq '.[].name' | xargs -I {} gh label delete {} --yes

# Créer les labels depuis le fichier
# (nécessite un script ou import manuel)
```

### Option B : Script bash

```bash
#!/bin/bash
REPO="BCISOFT/dvs-community"

# Bug types
gh label create "bug" --color "d73a4a" --description "Something isn't working" --repo $REPO
gh label create "enhancement" --color "a2eeef" --description "New feature or request" --repo $REPO
gh label create "recipe" --color "7057ff" --description "New recipe request" --repo $REPO
gh label create "documentation" --color "0075ca" --description "Documentation improvements" --repo $REPO
gh label create "question" --color "d876e3" --description "Further information is requested" --repo $REPO

# Status
gh label create "triage" --color "fbca04" --description "Needs initial review" --repo $REPO
gh label create "confirmed" --color "0e8a16" --description "Issue has been confirmed" --repo $REPO
gh label create "wontfix" --color "ffffff" --description "This will not be worked on" --repo $REPO

# Priority
gh label create "priority: critical" --color "b60205" --description "Critical priority" --repo $REPO
gh label create "priority: high" --color "d93f0b" --description "High priority" --repo $REPO
gh label create "priority: medium" --color "fbca04" --description "Medium priority" --repo $REPO
gh label create "priority: low" --color "0e8a16" --description "Low priority" --repo $REPO

# Components
gh label create "component: cli" --color "1d76db" --description "Related to the DVS CLI" --repo $REPO
gh label create "component: recipes" --color "1d76db" --description "Related to recipes" --repo $REPO
gh label create "component: storage" --color "1d76db" --description "Related to backup/storage" --repo $REPO
gh label create "component: tunnel" --color "1d76db" --description "Related to tunnel features" --repo $REPO

# Platform
gh label create "platform: macos" --color "c5def5" --description "macOS specific" --repo $REPO
gh label create "platform: linux" --color "c5def5" --description "Linux specific" --repo $REPO
gh label create "platform: docker-desktop" --color "c5def5" --description "Docker Desktop specific" --repo $REPO
gh label create "platform: orbstack" --color "c5def5" --description "OrbStack specific" --repo $REPO

# Community
gh label create "good first issue" --color "7057ff" --description "Good for newcomers" --repo $REPO
gh label create "help wanted" --color "008672" --description "Extra attention is needed" --repo $REPO
```

## 6. Topics (Tags du dépôt)

Ajouter ces topics au dépôt :
- `devspaces`
- `docker`
- `development-environment`
- `php`
- `wordpress`
- `prestashop`
- `developer-tools`
- `cli`

Via : Settings → About → Topics

## 7. Fichiers optionnels

### FUNDING.yml (sponsoring)

```yaml
# .github/FUNDING.yml
github: devspaces
custom: ["https://devspaces.cloud/pricing"]
```

### Dependabot (pas nécessaire - pas de code)

Non applicable pour ce repo.

## 8. Branch Protection

Pour le repo community, pas strictement nécessaire car il n'y a pas de code.
Optionnel si vous voulez protéger les fichiers de configuration.

## 9. Vérification finale

- [ ] README.md visible et correct
- [ ] Issue templates fonctionnels (tester avec New Issue)
- [ ] Discussions activées avec catégories
- [ ] Labels importés
- [ ] Topics ajoutés
- [ ] Liens fonctionnels (docs, Discord, etc.)

## 10. Annonce

Une fois le repo prêt :
1. Annoncer sur Discord
2. Ajouter le lien dans la documentation
3. Mentionner dans la CLI (`dvs feedback` ?)
