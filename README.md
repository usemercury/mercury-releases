# Mercury

A desktop client for message brokers — Azure Service Bus first. Browse,
send, receive, search and repair messages; manage queues, topics,
subscriptions and rules; work with several namespaces side by side.

This repository holds Mercury's **installers and release notes** only.

## Install

**Windows**

```powershell
winget install UseMercury.Mercury
```

Or download `Mercury_<version>_x64-setup.exe` (`_arm64-setup.exe` on ARM)
from the [latest release](../../releases/latest) and run it. It installs for
your user only and needs no administrator rights.

**macOS**

```sh
brew install --cask usemercury/tap/mercury
```

Or download `Mercury_<version>_universal.dmg` from the
[latest release](../../releases/latest), open it and drag Mercury into
**Applications**.

**Linux**

Download the `.deb`, `.rpm` or `.AppImage` from the
[latest release](../../releases/latest):

```sh
sudo apt install ./Mercury_<version>_amd64.deb      # Debian, Ubuntu
sudo dnf install ./Mercury-<version>-1.x86_64.rpm   # Fedora, RHEL
chmod +x Mercury_<version>_amd64.AppImage && ./Mercury_<version>_amd64.AppImage
```

Updating installs the new version over the old one; your saved connections,
keys and message schemas are kept.

## First launch: security warnings

Mercury's installers are not code-signed yet, so Windows and macOS warn
that they do not know the publisher. This is expected, and you only need
to get past it once per version.

**Windows: "Windows protected your PC"**

1. Click **More info**.
2. Check that the app is `Mercury_<version>_x64-setup.exe`, then click
   **Run anyway**.

If the browser blocks the download itself (Edge: "isn't commonly
downloaded"), open the downloads list, choose **⋯ → Keep → Show more →
Keep anyway**. If a company policy hides **Run anyway**, ask your IT team,
or use `winget install UseMercury.Mercury`.

**macOS: "Mercury cannot be opened" / "Apple could not verify…"**

1. Open Mercury once from **Applications** and close the warning (choose
   **Done**, not **Move to Bin**).
2. Open **System Settings → Privacy & Security**, scroll to **Security**,
   and click **Open Anyway** next to the message about Mercury.
3. Confirm with **Open Anyway** and your password or Touch ID.

Or, in Terminal: `xattr -dr com.apple.quarantine /Applications/Mercury.app`.
Since macOS Sequoia, Control-click → **Open** no longer skips the warning.
Homebrew prints the same steps after installing.

**Linux**

No warning. If the AppImage does not start, make sure it is executable
(`chmod +x`) and that FUSE is installed (`sudo apt install libfuse2`, or `libfuse2t64` on Ubuntu 24.04 and later).

## Connecting

Mercury connects with a connection string, a shared access key or SAS
token, or Microsoft Entra ID (browser sign-in, the Azure CLI, or a service
principal). Secrets are kept in your operating system's keychain, never in
plain files. Mercury talks only to the brokers and sign-in services you
configure; it sends nothing to its authors.

A built-in demo broker ("Connect to mock broker") lets you try everything
without an Azure namespace.

## Feedback and bugs

Use **Diagnostics** at the bottom of the sidebar: it copies the version,
platform and recent log lines (no secrets) to paste into a bug report.
Open an [issue in this repository](../../issues/new) with it, saying what
you did, what you expected and what happened instead.

## Licence

Mercury is free to use during the preview, including at work, under the
[Mercury Preview Licence](LICENSE). It is not open source. The open-source
components it includes are listed, with their licences, in
`THIRD-PARTY-NOTICES.txt`, installed with the app.
