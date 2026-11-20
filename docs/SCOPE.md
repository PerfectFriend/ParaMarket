# ParaMarket scope

## In scope

- App manifest schema and validation
- First-party catalog
- App SDK **contracts** (interfaces apps compile against)
- Host runtime requirements (session, permissions, revoke on lock/wipe)
- Example manifests and install notes

## Out of scope (other repos)

- BIP39 vault, PIN, keyboard → BIP39-SDK-GROK
- SimpleX wire protocol → RustSimplex / NeXXChat
- Shard storage / POR → NeXXuS Node
- Silver economy APIs → ParanoidX-Node

## Security baseline

- Apps get `NexxusSession` capabilities only
- No API to export mnemonic or PIN
- Permission prompts owned by host shell
- Signed manifests required from store-0.2 onward
