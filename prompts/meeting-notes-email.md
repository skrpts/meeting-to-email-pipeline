---
type: prompt
id: meeting-notes-email
title: Meeting Notes Email
description: "Task prompt for converting meeting notes into a well-formatted email summary"
tags: [Production, Communication, Metrics]
connections:
  - target: text-summarisation
    type: derived_from
  - target: company-style-guide
    type: references
---

## Purpose

Converts raw meeting notes into a professional, well-structured email suitable for distribution to attendees and stakeholders.

## Prompt

Using the summary and action items from the earlier stages, produce a well-formatted email summary. Include: attendees, key decisions, action items with owners, and next steps.

### Inputs

- **Meeting summary:** {{steps.previous.output}}
- **Action items:** {{steps.Action Item Extraction.output}}
