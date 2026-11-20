# ParaMarket

**NeXXuS application store & marketplace plane**

Catalog, app manifests, App SDK contracts, and the first-party shelf that runs on:

| Layer | Repo / system |
|-------|----------------|
| Identity + keyboard | [BIP39-SDK-GROK](https://github.com/PerfectFriend/BIP39-SDK-GROK) |
| Transport | SimpleX (`RustSimplex` / NeXXChat agent) |
| Storage mesh | NeXXuS Node |
| Economy (optional) | [ParanoidX-Node](https://github.com/PerfectFriend/ParanoidX-Node) |

Apps never receive mnemonic or PIN — only a scoped **session** after host unlock (PIN-only policy).

## What lives here

```
ParaMarket/
├── docs/                 architecture, threat notes for store
├── schema/               nexxus-app.json (manifest)
├── catalog/              first-party shelf listings
├── sdk/                  App SDK contracts (stubs → real)
├── runtime/              host runtime notes / reference
└── examples/             sample manifests & minimal apps
```

## First-party shelf (targets)

| Store id | Product |
|----------|---------|
| `nexxus.messenger` | NeXX / Paranoid messenger |
| `nexxus.radio` | Radio Armageddon client |
| `nexxus.comics` | Nasreddin |
| `nexxus.feed.cats` | Catstagram |
| `nexxus.game.oracle` | Unified Oracle / tarot games |
| `nexxus.game.madgammon` | MadGammon |
| `nexxus.game.arcade` | Snake + memory pack |
| `nexxus.market.nailix` | NailiX services market |
| `nexxus.isle` | Isle / community + economy UI |

## Manifest (preview)

See `schema/nexxus-app.schema.json` and `examples/nexxus.messenger.json`.

```json
{
  "id": "nexxus.messenger",
  "name": "NeXX Messenger",
  "version": "0.1.0",
  "permissions": ["transport.send", "transport.recv", "profile.read"],
  "entry": { "android": "com.nexxus.messenger.MainActivity" },
  "min_identity_sdk": "1.0.0",
  "publisher": "PerfectFriend"
}
```

## Roadmap (aligned with NeXXuS master plan)

1. **Store v0** — schema + static catalog + local install story  
2. **App SDK stub** — `onCreate(session)`, send/subscribe, private storage  
3. **Two pilot apps** installable end-to-end (messenger + one game)  
4. Signed updates and stricter permissions  

Platform plan: `BIP39-SDK-GROK` → `docs/NEXXUS_MASTER_PLAN.md` (Phase D = this repo).

## Policy

- No biometric unlock in platform hosts  
- Seed never on the wire or in app process APIs  
- Auditor gates with **Колян** per release train  

## License

MIT (unless a subdirectory states otherwise).
