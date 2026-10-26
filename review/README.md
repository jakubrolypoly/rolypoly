# Review

A small web page for reviewing a video and leaving timestamped notes. It runs entirely in your browser.

## What it does

* Pick a video from your own computer, or drag it onto the page. The file is never uploaded.
* Add notes at the current time. Click a timestamp to jump back to it. Edit or delete any note.
* Notes are saved in this browser, separately for each video (by file name and length).
* Copy all notes as plain text to paste into a chat.
* Send the notes straight to your Grok Bot through a webhook.

## Keyboard

* Space: play or pause
* C: write a note at the current time (Ctrl or Cmd + Enter saves it)
* Left and Right arrows: back or forward 1 second (hold Shift for 5 seconds)
* Comma and period: back or forward one frame

## How to connect your Grok Bot

1. Ask your Grok Bot to create a routine with a webhook trigger that treats incoming payloads as review notes.
2. Copy the webhook URL and the sender key from the routine panel.
3. Open Settings on the page (the gear) and paste them in.
4. Press Send test ping.

The URL and key are stored only in your browser's local storage. They are not part of the site.

## What gets sent

A POST with `Content-Type: application/json`:

```json
{
  "type": "review_notes",
  "app": "review-app",
  "version": "1.0.0",
  "video": { "name": "clip.mp4", "duration_s": 12.5 },
  "reviewer": "Sam",
  "sent_at": "2026-10-26T11:40:00.000Z",
  "notes": [ { "t_s": 3.2, "timecode": "0:03.2", "text": "Logo flickers" } ]
}
```

A test ping uses `"type": "test"` and an empty notes list. By default the key goes in an `Authorization: Bearer` header. Settings also let you use a custom header or a query parameter.

If the bot address does not accept requests from web pages (a CORS or network error), the page copies the notes to your clipboard so you can paste them instead.

## Hosting

It is one static file, `index.html`, with no build step. Put it in a GitHub repository and turn on GitHub Pages, or just open the file locally. The `.nojekyll` file tells GitHub Pages to serve the files as they are.
