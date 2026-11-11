# Beep IO

An Ollee Watch Forge app for two-way communication with android: pusher events + custom notifications.

## Files

- BeepIO1.18.js — The watch app. Load it through Ollee Forge.
- Beep_IO.prj.xml — The companion Tasker project. Import it into Tasker on your phone.

## Setup

1. Install Tasker and Gadgetbridge on your Android phone.
2. Load BeepIO1.18.js onto your watch through Ollee Forge, then add your watch to Gadgetbridge.
3. In Gadgetbridge, enable:
   - Settings → Developer options → Intent API → Allow 3rd party apps to change settings.
   - In the same menu → Allow Debug Commands.
   - Your watch’s Developer settings → Allow 3rd party apps to change settings.
   Restart Gadgetbridge.
4. In Tasker, long-press a project tab at the bottom → Import Project → select Beep_IO.prj.xml.
5. Open Beep-IO Initial Setup. In the first action, replace YOUR_WATCH_ADDRESS with your watch’s Bluetooth address from Gadgetbridge. Run the task, then connect the watch manually in Gadgetbridge.
6. Enable both imported profiles and open Beep IO on the watch. Close the Ollee phone app for normal use.

## Assign buttons

In Beep-IO Receive, add your actions inside the matching A1–A12 or L1–L12 If/End If blocks. All slots start empty.

Tap A or L 1–4 times. Hold either for 1.5 seconds to change layers. Layers 1, 2 and 3 select commands 1–4, 5–8 and 9–12.

## Send notifications

Use Tasker’s Perform Task → Beep-IO Send, with %par1 containing:

- NOTI1 through NOTI6: sound/light pattern.
- NOTI1|word: pattern plus text.
- NOTI1|DT:12|word: also displays 12 in the top digits.
- FINDWATCH: find-watch alert.
- STOP: stop the alert.

Maximum message length: 20 UTF-8 bytes, including commands. Create your own Tasker triggers to forward phone notifications.

The connection handoff profile disconnects Gadgetbridge while the Ollee app is open and reconnects afterward.
