<p align="center">
  <img src="docs/mobyd.svg" width="96" alt="MobyD logo" />
</p>

<h1 align="center">MobyD</h1>

<p align="center">
  A fast, native Git client for macOS — with repositories on your other machines, over SSH.
</p>

<p align="center">
  <a href="https://github.com/gyeongjin-kim/MobyD-releases/releases/latest"><img alt="Latest release" src="https://img.shields.io/github/v/release/gyeongjin-kim/MobyD-releases?label=release&color=2ed3e6"></a>
  <img alt="Platform" src="https://img.shields.io/badge/platform-macOS%20(Apple%20silicon)-lightgrey">
</p>

<p align="center">
  <a href="https://github.com/gyeongjin-kim/MobyD-releases/releases/latest/download/MobyD-macOS-arm64.dmg"><b>⬇ Download MobyD for macOS (.dmg)</b></a>
</p>

<p align="center">
  <img src="docs/graph.png" alt="MobyD commit graph" />
</p>

## Why "MobyD"?

GitKraken is named after the **Kraken**, the giant squid of sea legend. The giant squid has exactly one natural enemy: the **sperm whale**. The most famous sperm whale of all is **Moby Dick**, the white whale — hence **MobyD**.

MobyD started as an answer to the things we kept running into with GitKraken: it is heavy (a full Electron app), and it cannot work on a repository that lives on *another* computer. MobyD is a small native app (a 4 MB download) that treats a repository on your SSH-reachable PC the same as one on your laptop.

## What it does

- **Commit graph** with branches, tags, stashes and work in progress; staging by file, hunk or line.
- **Everyday Git** — commit, branch, merge, rebase (interactive too), cherry-pick, stash, worktrees, blame, file history, with **Undo / Redo**.
- **SSH repositories** — pick a host from your `~/.ssh/config`, browse its folders and open a repository there as if it were local. Nothing to install on the other machine except Git; macOS, Linux and Windows hosts work.
- **GitHub, GitLab and Gitea / Forgejo** — sign in, clone, and review or merge pull requests.
- Dark and light themes, English and Korean UI, built with Tauri 2, Rust and React.

## About this repository

This repository holds the release builds of MobyD and the update feed the app reads. Every release carries:

| File | |
|---|---|
| `MobyD-macOS-arm64.dmg` | The installer. The link above always serves the newest one. |
| `MobyD.app.tar.gz` | The signed archive a running MobyD downloads to update itself. |
| `latest.json` | The update feed: newest version, its signature and where to get it. |

## Install

1. Download **[MobyD-macOS-arm64.dmg](https://github.com/gyeongjin-kim/MobyD-releases/releases/latest/download/MobyD-macOS-arm64.dmg)** and drag MobyD into Applications.
2. MobyD is not notarized yet, so the first launch is blocked by Gatekeeper. Right-click MobyD → **Open**, or run:

   ```bash
   xattr -dr com.apple.quarantine /Applications/MobyD.app
   ```

Requires macOS on Apple silicon and Git 2.36+.

## Updates

MobyD checks this feed at launch and every few hours. When a newer version exists, an **Update** button appears in the top bar; one click downloads it, verifies its signature, installs it and restarts the app. You can also check by hand under Preferences → General.
