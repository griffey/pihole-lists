# pihole-lists

Custom Pi-hole blocklists for GriffeyNet. Both Pi-holes subscribe to these by URL.

## Lists

| File | What it blocks | Subscribe URL |
|---|---|---|
| `griffeynet-privacy.txt` | Device telemetry and calls to shut-down clouds (Wemo, Kevo) that the general-purpose lists miss | `https://raw.githubusercontent.com/griffey/pihole-lists/main/griffeynet-privacy.txt` |

## Editing

1. Edit the file and push to `main`.
2. Each Pi-hole picks up the change at its next weekly list update. To apply it now: Pi-hole web UI → **Tools → Update Gravity**, on each Pi-hole.

Format notes (Pi-hole v6):

- `||example.com^` blocks `example.com` and every subdomain.
- `example.com` on its own blocks only that exact name.
- Lines starting with `#` are comments.

Before adding something, check it isn't needed for the device to work. Blocking a domain a device depends on breaks it quietly, and the cause is hard to spot later. A comment on each group saying why it's safe makes later cleanup easy.

## Adding a new list

Add a new `.txt` file here, then in each Pi-hole: **Lists → Add a new subscribed list**, using
`https://raw.githubusercontent.com/griffey/pihole-lists/main/<file>.txt`, then **Tools → Update Gravity**.
