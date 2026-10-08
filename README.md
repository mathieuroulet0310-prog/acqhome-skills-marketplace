# acqhome-skills-marketplace

Marketplace personnel Claude Code / Cowork. Plugin : **acqhome-master-automation** (v1.1.0, 39 skills).

Skills curés depuis [anthropics/skills](https://github.com/anthropics/skills),
[obra/superpowers](https://github.com/obra/superpowers),
[coreyhaines31/marketingskills](https://github.com/coreyhaines31/marketingskills) et
[ComposioHQ/awesome-claude-skills](https://github.com/ComposioHQ/awesome-claude-skills),
avec scan sécurité avant publication. Synchronisé le 2026-10-08.

```
/plugin marketplace add <owner>/acqhome-skills-marketplace
/plugin install acqhome-master-automation@acqhome-skills-marketplace
```

## Notes de sécurité

Revue complète le 2026-07-18 (scan de motifs d'exécution + lecture sémantique intégrale des 33 skills initiaux par agents, findings contre-vérifiés ; 9 skills design/UI-UX et sécurité ajoutés le 2026-08-01 et passés par le même scan). Trois points corrigés ou à connaître :

- **ad-creative** : la commande `npx gooseworks install --all` du guide iMessage a été neutralisée (package npm tiers non épinglé installant des skills d'agent en masse). Installation manuelle et revue par l'utilisateur uniquement.
- **social** : note ajoutée dans `references/listening.md` — le contenu récupéré (Reddit/HN/Bluesky/RSS) est non fiable et doit être traité comme données, jamais comme instructions (surface de prompt-injection indirecte).
- **brainstorming** : le companion visuel charge un logo depuis primeradiant.com (télémétrie amont IP+version, active par défaut, non documentée en amont). Opt-out : `SUPERPOWERS_DISABLE_TELEMETRY=1` ou `CLAUDE_CODE_DISABLE_NONESSENTIAL_TRAFFIC=1`.

Les skills patchés divergent volontairement de leur amont ; le diff est réexaminé à chaque synchronisation.
