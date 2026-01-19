---
layout: post
title: "Pencil2D Goes Universal on macOS"
tagline: "Native performance for both Intel and Apple Silicon Macs"
categories: "News Release"
author: "Pencil2D Team"
published: true
comments: true
---

## Pencil2D is now a universal macOS app!

Whether you're running a classic Intel Mac or one of the newer Apple Silicon models (M1, M2, M3, or M4), you can now enjoy Pencil2D with native performance optimized for your hardware.

Download: **[Pencil2D Nightly Builds]({{ "/download/nightly/" | relative_url }})**

This is available immediately in our Nightly Builds, stable releases will follow in the near future.

## What's Changed?

Previously, Pencil2D for macOS was built only for Intel chips. If you're on an Apple Silicon Mac (M1 or newer), you've been running Pencil2D through Rosetta 2, Apple's translation layer. While Rosetta works well, native ARM code can run faster, uses less power, and makes better use of your Mac's capabilities.

We've now built a **Universal App**, which automatically detects your Mac's architecture and runs in the optimal mode on both Intel and Apple Silicon Macs.

## The Future with Qt6

You may notice the user interface looks slightly different. This is because we've upgraded our UI framework from Qt5 to Qt6. This transition was necessary to support modern macOS features like universal binaries. Additionally, we'd like to build Pencil2D on a modern, actively maintained foundation for future development.

## Download Nightly Builds

We encourage all macOS users, especially those on M-series chips, to give the new universal app a try. Your testing helps us polish the experience before the official stable release.

Check out the **[nightly builds]({{ "/download/nightly/" | relative_url }})**!

## Your Feedback Matters

Have questions or want to report a bug? Share your thoughts on [our User Forum](https://discuss.pencil2d.org/) or join the chat on our [Discord server](https://discord.gg/8FxdV2g).

Happy animating!
