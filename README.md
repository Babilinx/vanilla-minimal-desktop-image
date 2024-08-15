# Vanilla OS Minimal Desktop Image

Containerfile for building a Vanilla OS Minimal Desktop image.

This image is based on top of [`vanillaos/core`](https://github.com/Vanilla-OS/core-image/pkgs/container/core) and offers the default
Vanilla OS Desktop experience with GNOME with some things in less.

**Not everything has been tested! Use with precautions!**

## Differences with the desktop image

* Added GNOME Tweaks package
* Removed GNOME System Monitor
* Removed default GNOME Shell extensions
* Hided Vanilla Tour in the app drawer
* Hided Help in the app drawer
* Hided Input Method in the app drawer
* And some other small changes

## Build

> [!NOTE]
> The fsguard compiled plugin `.so` file should be downloaded from the [latest release](https://github.com/Vanilla-OS/vib-fsguard/releases/latest) and be placed under a `plugins` directory beside the `recipe.yml` file.

```bash
vib build recipe.yml
podman image build -t babilinx/minimal-desktop .
```

## Verify Image Build Provenance Attestation

> [!NOTE]
> This is actually not supported.

All the image builds/pushes are attested for build provenance and integrity using the [attest-build-provenance](https://github.com/actions/attest-build-provenance) action. The attestations can be verified [here](https://github.com/Vanilla-OS/desktop-image/attestations) or by having the latest version of [GitHub CLI](https://github.com/cli/cli/releases/latest) installed in your system. Then, execute the following command:

```sh
gh attestation verify oci://ghcr.io/babilinx/minimal-desktop:main --owner Babilinx
```
