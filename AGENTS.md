# Kinayad — Contexte projet (frontend)

Frontend statique (HTML/CSS/JS sans build) déployé sur Vercel. Dashboard du
praticien + landing page.

> À lire en premier à chaque session. Le contexte complet (équipe, gouvernance,
> protocole, leçons) est dans `kinayad-backend/AGENTS.md` — ce fichier-ci ne
> répète que ce qui est spécifique au frontend.

## Règles propres à ce dépôt

- **Pas de push direct** : Hermès n'a pas de token sur ce dépôt — les branches
  sont poussées par Claude Code (via le clone local) ou avec un accès dédié.
- **Toujours vérifier que les endpoints appelés existent côté backend** (main ou
  branche mergée) avant d'intégrer un appel API — un commit frontend dépendant
  d'un endpoint non mergé a déjà été retiré en revue.
- **Slug du tenant** : vient du compte connecté (`/auth/me`), jamais codé en dur.
- **Auth** : token opaque en `sessionStorage`, envoyé en `Authorization: Bearer`.
- **Validation JS** : `node --check` sur le `<script>` extrait avant de committer.
- API : `https://kinayad-api.onrender.com` (prod).

## État courant

- Auth (connexion/inscription, fin du mot de passe global) : **FAIT** — PR #1
  mergée et déployée avec la PR #5 backend le 30/08. Isolation vérifiée en
  vraie prod (navigateur réel, deux cabinets distincts).
- Adresse du cabinet : **FAIT** — backend mergé (PR #8) et frontend mergé
  (`2e6f6e4`), champ « Adresse du cabinet » déployé en prod sur Vercel.
