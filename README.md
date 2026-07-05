# HOA Board Tracker

Executive summaries, complaint tracking, and performance index for Parkside Heights HOA board operations.

Populated automatically by SlackAgent workflow `11-hotmail-ingest` (n8n).

## Layout

```
data/
  summaries/{YYYY-MM}/{slug}.md    # Financial/packet exec summaries
  complaints/open/{id}.json        # Open resident complaints
  complaints/closed/{id}.json      # Replied complaints
  complaints/thread-index.json     # Slack thread_ts → complaint id
  ingest/processed.json            # Processed Outlook message IDs
  performance/index.json           # Rolling metrics index
```

## Setup

1. Create this repo on GitHub (`dayamjz/hoa-board-tracker`).
2. Add a GitHub PAT with **Contents: Write** to SlackAgent `.env` as `HOA_GITHUB_TOKEN`.
3. Run `npm run n8n:setup-hotmail` in SlackAgent after Outlook OAuth is configured.

Initial seed files are committed by the first ingest run.
