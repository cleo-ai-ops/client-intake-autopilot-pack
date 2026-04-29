# Free n8n Freelance Lead Scoring Workflow — Setup Guide

This free workflow gives freelancers a no-code starting point for routing inbound leads before booking calls.

## What you get

- An n8n form trigger for a client inquiry
- A code node that scores budget, timeline, decision-maker clarity, scope clarity, and project detail
- HOT / WARM / COLD routing
- Plain-text response nodes that you can replace with email, Slack, Google Sheets, CRM, or calendar actions

## 15-minute setup

1. Download `freelance-lead-scoring-workflow.json`.
2. In n8n, go to **Workflows → Import from File** and select the JSON.
3. Open the **Lead Intake Form** node and change the path if you want a different URL.
4. Open **Score Lead** and adjust thresholds to match your business:
   - `HOT`: good budget, clear scope, real decision-maker, workable timeline.
   - `WARM`: possible fit but needs clarification.
   - `COLD`: low budget, unclear scope, or no clear buyer.
5. Test with the sample leads in `SAMPLE-LEADS.md`.
6. Replace response nodes with your real next action:
   - HOT → booking link or qualified-lead email.
   - WARM → clarification questions.
   - COLD → polite decline or paid diagnostic offer.

## Suggested threshold tuning

- High-ticket consultant: raise HOT to 85+ and reduce points for vague timelines.
- Productized service: keep HOT around 75–80 and prioritize scope clarity.
- Agency/studio: add a field for stakeholder count and subtract points for unclear approval.

## Common n8n notes

- This workflow is intentionally local/free: it does not require paid APIs.
- Form node behavior can vary slightly by n8n version; if import warnings appear, recreate the form fields using the labels in the JSON.
- The scoring code expects the form field labels to stay the same. If you rename a field, update the matching key in **Score Lead**.
- Before using with real clients, replace placeholder response text with your own tone and privacy language.

## When to use the paid spreadsheet kit

Use the paid kit when you want the same scoring logic in Google Sheets/Excel with formulas, sample rows, intake questions, reply scripts, and a weekly review process. The workflow is a lightweight automation entry point; the spreadsheet kit is the operating system for managing leads over time.
