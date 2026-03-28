# APK Repo

This repository contains packaging sources under `packages/` and the published
static APK repository contents under `repo/`.

## Layout

- `packages/<name>/`: source files, package definitions, and build script for one APK
- `repo/`: static APK repository content intended to be published to GitHub Pages or another HTTP file host

## Build alauda-permit-layout

```bash
cd packages/alauda-permit-layout
./build.sh
```

Build output is written to `packages/alauda-permit-layout/out/`.

To publish later, copy the signed public key to `repo/melange.rsa.pub` and sync
package outputs into `repo/x86_64/` and `repo/aarch64/`.

Only publish the public key. Never commit the private key.

## Sync build output into repo/

After building one package, sync its signed APK repository contents into `repo/`:

```bash
./scripts/sync-package-to-repo.sh alauda-permit-layout
```

If omitted, the package name defaults to `alauda-permit-layout`.
