---
type: prompt
id: meeting-notes-email
title: Meeting Notes Email
description: "Task prompt for converting meeting notes into a well-formatted email summary"
tags: [Production, Communication, Metrics]
inputs:
  meeting_notes:
    label: "Meeting Notes"
    description: "Raw meeting notes, transcript, or summary to convert into an email"
    example: "Paste your meeting notes or transcript here"
    required: true
    type: file
    accept: ".txt,.md,.docx,.pdf"
  recipients:
    label: "Recipients"
    description: "Who this email is for — helps set the right tone and detail level"
    example: "Engineering team + product manager"
    required: false
    type: text
connections:
  - target: text-summarisation
    type: derived_from
  - target: company-style-guide
    type: references
---

## Purpose

Converts raw meeting notes into a professional, well-structured email summary suitable for distribution to attendees and stakeholders.

## Prompt

You are an executive assistant. Convert the meeting notes below into a professional email summary.

### Meeting Notes

{{input.meeting_notes}}

### Recipients

{{input.recipients}}

### Instructions

Produce a well-formatted email summary including:
- Subject line
- Attendees (extracted from the notes)
- Key discussion points (2-3 sentences each)
- Decisions made (with context)
- Action items with owners and deadlines
- Next steps

Keep the tone professional and concise. Recipients should be able to scan the email in under 2 minutes.
