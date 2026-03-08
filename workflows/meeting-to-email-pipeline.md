---
type: workflow
id: meeting-to-email-pipeline
title: Meeting to Email Pipeline
description: "Records meeting notes, summarises key points, extracts actions, and formats as email"
tags: [Production]
connections:
  - target: text-summarisation
    type: uses
  - target: action-item-extraction
    type: uses
  - target: meeting-notes-email
    type: uses
---

## Overview

This workflow takes raw meeting notes, processes them through summarisation and action item extraction, then formats the output as a professional email ready for distribution.

## Pipeline Stages

### Stage 1: Summarise

Invoke the **text-summarisation** skill against the raw meeting notes to produce a concise summary of key points and decisions.

### Stage 2: Extract Actions

Invoke the **action-item-extraction** skill against the raw meeting notes to capture all follow-up tasks with responsible parties and deadlines.

### Stage 3: Format Email

Invoke the **meeting-notes-email** prompt, combining the summary and action items into a well-formatted email. Apply the company style guide for tone and formatting consistency.

## Output

A formatted email containing:

- Meeting date, attendees, and purpose
- Key decisions made
- Action items with owners and deadlines
- Next steps and follow-up date
