---
name: compte-rendu-reunion
description: Rédige le compte rendu professionnel d'une réunion de recueil des besoins client à partir de sa transcription. À utiliser quand l'utilisateur fournit ou désigne une transcription de réunion client et demande un compte rendu, une synthèse des besoins ou une préparation du cahier des charges.
---

# Compte rendu de réunion de recueil des besoins

Transforme la transcription brute d'une réunion avec le client en un compte rendu structuré, fidèle et directement exploitable pour rédiger le cahier des charges (phase 1 du projet).

## Fichiers

| Élément | Emplacement | Versionné |
|---------|-------------|-----------|
| Modèle de sortie | `.claude/skills/compte-rendu-reunion/template.md` | oui |
| Transcription (entrée) | `reunions/transcriptions/` | **non** |
| Compte rendu (sortie) | `reunions/comptes-rendus/AAAA-MM-JJ-compte-rendu-besoins.md` | **non** |

Les transcriptions et comptes rendus contiennent des échanges avec le client : ils ne doivent jamais être commités ni poussés. Le `.gitignore` les exclut ; ne jamais le contourner (`git add -f` interdit pour ces dossiers).

## Procédure

1. **Lire la transcription en entier** avant d'écrire quoi que ce soit. Si l'utilisateur n'a pas indiqué le fichier, regarder dans `reunions/transcriptions/` ; s'il y en a plusieurs, demander lequel utiliser.
2. **Lire `template.md`** et suivre sa structure et ses titres, sans en inventer ni en retirer. Une section sans contenu dans la transcription reste présente avec la mention « Non abordé lors de la réunion ».
3. **Extraire et classer** les informations :
   - contexte du client et de son activité ;
   - objectifs poursuivis par le site ;
   - besoins fonctionnels, avec leur priorité (voir ci-dessous) ;
   - contraintes (budget, délais, technique, juridique) ;
   - identité visuelle, contenus, éléments que le client doit fournir ;
   - décisions prises ;
   - points ouverts ;
   - actions à mener (qui, quoi, échéance).
4. **Rédiger** le compte rendu dans `reunions/comptes-rendus/`, avec la date de la réunion dans le nom du fichier. Si la date est introuvable, la demander.
5. **Vérifier** avant de rendre la main :
   - chaque besoin, chiffre, date et nom du compte rendu figure bien dans la transcription ;
   - aucune section du modèle n'a disparu ;
   - le fichier est bien ignoré par Git : `git check-ignore -v <fichier>` doit renvoyer une règle.
6. **Résumer** à l'utilisateur, en quelques lignes, les besoins principaux et surtout les points à confirmer. Ne pas commiter.

## Règles de rédaction

- **Fidélité** : ne rien inventer, ne rien extrapoler. Un besoin n'existe que si le client l'a exprimé ou validé. Les idées proposées par l'utilisateur et non validées par le client vont dans « Points ouverts », pas dans les besoins.
- **Incertitude** : ce qui est ambigu, contradictoire ou dit à demi-mot est marqué **« À confirmer »**, avec la citation courte ou la raison du doute.
- **Priorités** : classer chaque besoin en *Indispensable*, *Important* ou *Souhaitable*. Se fonder sur les mots du client ; à défaut, mettre « Priorité à définir ».
- **Reformulation** : transformer l'oral en phrases claires et neutres, à la troisième personne (« La cliente souhaite… »). Supprimer hésitations, répétitions, digressions et échanges sans lien avec le projet.
- **Citations** : conserver entre guillemets, en les courtes, les formulations marquantes du client (vocabulaire métier, ton souhaité, expressions décisives).
- **Précision** : conserver tels quels les chiffres, dates, noms propres, tarifs, horaires et références évoqués.
- **Ton** : professionnel, factuel, concis. Pas de jugement ni de commentaire sur le client. Écrire en français.
- **Données personnelles** : ne reprendre que ce qui est utile au projet. Écarter les confidences sans rapport avec le besoin (santé, vie privée, litiges).
- **Erreurs de transcription** : l'outil de transcription peut déformer des mots (noms propres, termes techniques). En cas de doute, ne pas deviner : marquer « À confirmer ».

## Après le compte rendu

Le compte rendu sert de base au cahier des charges. Le valider avec l'utilisateur, puis avec le client, avant de passer à l'étape suivante.
