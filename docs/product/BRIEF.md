# Product brief

Durable product intent. Not a session log.

## Problem

macOS users need a small, keyboard-first clipboard history that stays local and does not require a paid subscription.

## Target users

macOS 14+ users who copy text and images often and want search, pin, and paste-without-format.

## Primary workflow

1. Copy as usual.
2. Open Maccy with ⇧⌘C or the menu-bar icon.
3. Search or arrow to an item.
4. Enter to copy, ⌥Enter to paste, ⌥⇧Enter to paste without formatting.

## Desired final artifact / outcome

A maintained fork of [p0deje/Maccy](https://github.com/p0deje/Maccy) at `~/Developer/Maccy`, able to take local changes and open PRs to upstream.

## Scope

- Native Swift macOS app in this checkout
- Upstream-compatible changes preferred unless a decision says otherwise

## Non-goals

- Rewriting as a new product under a different name
- Changing the MIT license
- Using unofficial download sites
- Installing the Homebrew cask as a substitute for this source tree

## Product constraints

- License: MIT (Copyright 2025 Alex Rodionov)
- Minimum OS: macOS Sonoma 14
- Sandboxed; auto-paste needs Accessibility
- Sparkle updates currently follow upstream `appcast.xml` → GitHub Releases

## Acceptance direction

The fork builds and tests in Xcode. Local changes stay reviewable against `upstream/master`.
