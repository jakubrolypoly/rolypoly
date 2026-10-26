# Review

A small web page for reviewing a video and leaving timestamped notes. It runs entirely in your browser. Version 1.1.0.

Open the page, pick a video, write notes, then copy them and paste them to whoever needs them. Nothing is uploaded.

## What it does

* Pick a video from your own computer, or drag it onto the page. The file stays on your computer. The player sits on the left, with the note box under it, and the notes list on the right. On a narrow screen the notes list stacks under the player.
* Add notes at the current time. Click a timestamp to jump back to it. Edit or delete any note.
* Drop a pin on the frame for a note. Pins are numbered circles on the picture. The number matches that note's place in the list, starting at 1. A note can also be saved with no pin.
* Notes are saved in this browser, separately for each video (by file name and length). A pin is saved with its note. Older notes that have no pin still load.
* After a refresh, the video file has to be opened again. If any notes are saved, a Saved notes panel lists each video, how many notes it has, and when they were last edited. Reopen the same file to continue. You can view or copy those notes before the video is open.
* Copy all notes as plain text. The first line is the video name and duration. Each note is one line after that.

## Keyboard

* Space: play or pause
* Enter: add the note. Shift+Enter adds a line break while typing. Ctrl or Cmd+Enter still saves an edit.
* C: put the note time at the current frame and focus the note field
* P: turn pin mode on or off. Then click or tap the picture to drop a pin. The note box is focused so you can type. Drag a pin to move it. The x on the pin, Remove on a pin that is not saved yet, or Remove pin on the note takes the pin off and keeps the note.
* Left and Right arrows: back or forward 1 second (hold Shift for 5 seconds)
* Comma and period: back or forward one frame

Pins show only while the playhead is within about 1 second of that note, including when playback is paused on the note. Click a note in the list to jump to it and highlight its pin.

Pin positions are fractions of the real picture, from 0 to 1, so a tall video in a wide frame still lines up. The black bars around the picture are not part of the pin area.

## Saved on this device

Notes stay in this browser until you remove them. Refreshing the page does not delete them. The video file is not stored, so you pick it again. The same file name and length bring the notes and pins back.

Each saved set keeps a last edited time. Clear all asks before it removes the notes for the open video. Delete saved notes, on each row of the Saved notes panel, asks before it removes that video's notes.

## What copy produces

Copy all notes puts plain text on the clipboard:

```
clip.mp4 (00:00:12.5)
00:00:03.2 [pin x=41% y=29%] Logo flickers
00:01:23.4 Second note
```

The pin text is included only when that note has a pin. `x` and `y` are percentages of the picture. Times use hours, minutes, seconds, and tenths.

## Hosting

It is one static file, `index.html`, with no build step. Put it in a GitHub repository and turn on GitHub Pages, or just open the file locally. The `.nojekyll` file tells GitHub Pages to serve the files as they are.
