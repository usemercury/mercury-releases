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

Or download `Mercury_<version>_x64-setup.exe` (or `_arm64-setup.exe`) from
the [latest release](../../releases/latest). The installer is not
code-signed yet: if Windows shows "Windows protected your PC", choose
**More info → Run anyway**.

**macOS**

```sh
brew install --cask usemercury/tap/mercury
```

Or download the `.dmg` from the [latest release](../../releases/latest).
Mercury is not notarised by Apple yet: if macOS says it cannot be opened,
allow it once in **System Settings → Privacy & Security → Open Anyway**, or
run `xattr -dr com.apple.quarantine /Applications/Mercury.app`.

**Linux**

Download the `.deb`, `.rpm` or `.AppImage` from the
[latest release](../../releases/latest):

```sh
sudo apt install ./Mercury_<version>_amd64.deb
```

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
