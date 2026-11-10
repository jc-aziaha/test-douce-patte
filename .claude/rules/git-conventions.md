# Conventions Git : branches et commits

## Types

Les mêmes types servent pour les branches et pour les commits :

| Type | Usage |
|------|-------|
| `feat` | nouvelle fonctionnalité |
| `fix` | correction de bug |
| `docs` | documentation uniquement (README, CLAUDE.md, rules) |
| `refactor` | réécriture sans changement de comportement |
| `test` | ajout ou modification de tests |
| `chore` | maintenance, configuration, dépendances |

## Branches

Format : `<type>/<description-courte>`

- description en minuscules, en kebab-case, sans accents, 2 à 5 mots
- une branche = un sujet, créée depuis `main` à jour
- exemples : `feat/formulaire-contact`, `fix/validation-email`, `docs/conventions-git`

## Commits

Format : [Conventional Commits](https://www.conventionalcommits.org/fr/v1.0.0/)

```
<type>(<portée optionnelle>): <description>

<corps optionnel : le pourquoi, pas le comment>
```

- description en français, à l'impératif présent (« Ajoute », « Corrige »), sans point final, 72 caractères maximum
- portée optionnelle pour préciser la zone touchée : `feat(leads): ajoute l'export CSV`
- un commit = un changement logique ; ne pas mélanger plusieurs sujets
- exemples :
  - `feat(contact): valide les données du formulaire côté serveur`
  - `fix(auth): corrige l'expiration du lien de réinitialisation`
  - `docs: ajoute les conventions de nommage Git`
