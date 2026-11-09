# osa-aliexpress-callback

Pagina **statica** di callback OAuth per l'app **AliExpress Affiliates API** di
**OSA — Offerte Smart by Albertone**.

## Scopo
AliExpress richiede una **Callback URL HTTPS** verso cui reindirizzare dopo
l'autorizzazione. Questa pagina serve solo a **ricevere quel reindirizzamento**
nel browser. Il `code` di autorizzazione resta nella barra degli indirizzi e
viene usato **manualmente**, in locale, per ottenere il token (entro ~3 minuti).

## Sicurezza (per progetto)
- Pagina **100% statica**, **nessun JavaScript**.
- **Non** legge, **non** mostra, **non** registra e **non** trasmette il
  parametro `code` (né altri parametri).
- **Nessuna** risorsa esterna (niente CDN/font/analytics/tracker).
- **Nessuna** App Key, App Secret, token o segreto nel repository.
- Lo scambio `code` → token avviene **fuori da questa pagina**, in locale sul Mac,
  dove restano App Key/Secret.

## Contenuto
- `index.html` — la pagina di callback.
- `.nojekyll` — disattiva l'elaborazione Jekyll su GitHub Pages (serve i file così come sono).

## Pubblicazione (GitHub Pages)
Repository dedicato e pubblico `osa-aliexpress-callback`, GitHub Pages da branch
`main` (cartella root). URL risultante:

```
https://<tuo-username-github>.github.io/osa-aliexpress-callback/
```

Quell'URL esatto va inserito come **Callback URL** nel modulo AliExpress Open Platform.
