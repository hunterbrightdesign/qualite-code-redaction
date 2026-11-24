# Qualité du code et de la rédaction

Skill francophone pour vérifier une conception logicielle, corriger une application ou réviser un texte en préservant les faits et la voix de son auteur.

## Installer dans un projet sur macOS ou Linux

1. Récupérer ce dépôt avec Git ou télécharger et extraire son archive ZIP.
2. Ouvrir un terminal **à la racine du dépôt téléchargé**, dans le dossier qui contient ce README.
3. Dans le bloc ci-dessous, remplacer `/chemin/vers/mon-projet` par le chemin d’un projet existant. Les guillemets permettent d’utiliser un chemin contenant des espaces.

```sh
(
  set -eu
  projet="/chemin/vers/mon-projet"
  nom="qualite-code-redaction"
  source_skill="$(pwd)/.claude/skills/$nom"
  test -f "$source_skill/SKILL.md"
  cd "$projet"
  for cible in ".claude/skills/$nom" ".agents/skills/$nom"; do
    if [ -e "$cible" ] || [ -L "$cible" ]; then
      echo "Installation interrompue : $cible existe déjà." >&2
      exit 1
    fi
  done
  mkdir -p .claude/skills .agents/skills
  cp -R "$source_skill" ".claude/skills/$nom"
  ln -s "../../.claude/skills/$nom" ".agents/skills/$nom"
)
```

Le projet dispose ainsi d’une seule copie des instructions, accessible depuis les deux répertoires de skills. Pour une installation manuelle sur un système sans liens symboliques, copier le dossier source complet `.claude/skills/qualite-code-redaction` dans chacun des répertoires `.claude/skills/` et `.agents/skills/` du projet cible.

## Utilisation

Ouvrir le projet cible dans une nouvelle session et sélectionner `qualite-code-redaction` dans la liste des skills. Exemples de demandes :

- « Vérifie que la réponse de cette API correspond aux champs lus par son client. »
- « Corrige seulement les fautes de ce message en conservant le tutoiement. »

Les [cas d’essai](evals/cas.md) donnent les demandes et les critères de réussite.
