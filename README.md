# Ascension System

A gamified workout and habit tracker inspired by *Solo Leveling*. You are a Hunter, every workout is a Gate, and experience points, levels, ranks (E to S), stats and daily streaks reward showing up. It is an installable web app (PWA) on Firebase, built for one person and a handful of friends and family, so it favours simplicity and the free tier over scale.

**Live:** https://solo-leveling-fdd0f.web.app

## Contents

- [What it does](#what-it-does)
- [How it is built](#how-it-is-built)
- [Security notes](#security-notes)
- [Running your own copy](#running-your-own-copy)

## What it does

- Daily routines and custom exercises that award experience, with streaks that can weaken and recover.
- An avatar that levels up and equips items, with tiers, mystery boxes and a friends leaderboard.
- Past-day logging, multiple routines, a warm-up box and offline use with sync on reconnect.
- Email verification and password recovery, with a username login alongside email.

## How it is built

- A single `index.html` with inline JavaScript and CSS, no build step.
- Firebase Authentication, Cloud Firestore and Hosting.
- A service worker for offline use, a web manifest and generated icons.

## Security notes

The Firebase web configuration in `index.html` is public by design. Access is controlled by `firestore.rules`, which:

- let a signed-in user write only their own document,
- block users from granting themselves administrator, ban or email-exemption flags,
- validate usernames on the server side, because names are rendered into the page.

## Running your own copy

1. Create a Firebase project with Authentication (email and password) and Firestore.
2. Replace the `firebaseConfig` object in `index.html` with your own project's values and the project id in `.firebaserc`.
3. Deploy the rules and the site with `firebase deploy`.

## Licence

MIT. See [LICENSE](LICENSE).
