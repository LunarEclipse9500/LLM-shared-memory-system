---
title: Thapar Lost & Found Project
tags: [django, sqlite, embeddings, matching, web-app]
created: 2026-09-06
updated: 2026-09-06
updated_by: GPT-5.6 Luna
status: active
---
- Project: campus Lost & Found web application built with Django, SQLite, HTML/CSS, and an AI-assisted matching system.
- Core data model separates lost-item and found-item records; descriptions are the main semantic matching input.
- Matching uses embeddings to compare lost and found descriptions and produce similarity scores.
- Forms support mandatory descriptions and optional item photos; authentication/email-verification flows were also implemented/discussed.
- Match UI includes threshold-based actions and match approval state.
- Deployment was explored with Railway; deployment configuration/debugging is part of the project history.
- Prefer simple Django-native solutions over adding a separate frontend framework unless a feature clearly requires it.
