# profilarr-database

Fork personale di [Dictionarry-Hub/database](https://github.com/Dictionarry-Hub/database) per la gestione dei profili qualità custom su Profilarr.

## Scopo

- Preservare profili e custom format personalizzati in caso di reset del container/volume
- Sincronizzarsi automaticamente con il database upstream ogni settimana
- Ricevere notifiche Discord ad ogni modifica

## GitHub Actions

| Workflow | Trigger | Descrizione |
|---|---|---|
| `sync-upstream.yml` | Ogni domenica 03:00 UTC + manuale | Merge delle novità da `Dictionarry-Hub/database` nel fork |
| `notify.yml` | Push su `stable` / `dev` | Notifica Discord con autore, branch e messaggio del commit |

## Secrets richiesti

| Secret | Valore |
|---|---|
| `DISCORD_WEBHOOK` | URL webhook del canale Discord di notifica |

## Gestione conflitti

Se l'upstream modifica un file che hai personalizzato, `sync-upstream.yml` fallisce e GitHub invia una notifica. Risolvi il conflitto manualmente e pusha su `stable`.

## Collegamento a Profilarr

**Settings → Database → Link Repository:**
`https://github.com/bido1990/profilarr-database`
