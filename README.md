# Nerve Studios | Versions

Public version manifests for Nerve Studios FiveM scripts, one
`nerve_<script>.json` per script. The `nex_*` and `nexdev_*` files serve the
legacy NEX.dev scripts and stay as they are.

Each file is fetched once per start by the script's server-side version check
(`server/version.lua`; legacy scripts use `version_check.lua`). The console
prints "Up to date" when the remote `version` matches the script's
`fxmanifest.lua` `version`, and a boxed update notice with the changelog and
download links when the remote one is higher. Server owners can turn it off
with `set nerve:versioncheck false`.

## JSON shape

```json
{
    "version": "1.0.2",
    "release_date": { "day": 28, "month": 5, "year": 2026 },
    "notes": "Short summary of what changed in this release."
}
```

## Release process

1. Cut the release in the script's private repo (bump `fxmanifest` `version`).
2. After the new version is live on the Cfx.re Portal, update the matching
   `<script>.json` here through a PR.
3. Servers running an older build see the update notice on their next restart.
