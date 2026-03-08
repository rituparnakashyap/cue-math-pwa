# Cuemath PWA Launcher

A Progressive Web App (PWA) wrapper that lets you install [Cuemath](https://leap.cuemath.com) on a Chromebook as a standalone app.

## Why this exists

My child uses Cuemath on a Chromebook. The ideal experience would be to install `leap.cuemath.com` directly as a PWA so it behaves like a native app. However, the Cuemath site has a bug: when you install it as a PWA and reopen it later, Chrome restores the last visited session URL (e.g. `leap.cuemath.com/static/***`) instead of the home page, breaking the app on every relaunch.

This repo works around that by acting as a thin launcher hosted on GitHub Pages (`rituparnakashyap.github.io/cue-math-pwa`). The PWA is installed from this stable URL, which always opens correctly. A single button then navigates to `leap.cuemath.com/home` in the same window, giving a seamless full-screen experience.

## How it works

1. The PWA is installed from `rituparnakashyap.github.io/cue-math-pwa`
2. On launch, the user sees a branded splash screen with a "Start Math Lesson" button
3. Clicking the button navigates to `leap.cuemath.com/home` within the same PWA window
4. A service worker caches the launcher shell so it loads instantly even offline

## Setup

This is a static site — just push to the `main` branch and GitHub Pages serves it automatically.

To reinstall on Chromebook after any manifest change: uninstall the existing PWA first, then reinstall from the URL above.
