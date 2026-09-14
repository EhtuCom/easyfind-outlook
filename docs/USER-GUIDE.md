# EasyFind – user guide

## Opening EasyFind

In Outlook's mail view, ribbon tab **Home** (Inicio), group **EHTU EasyFind** (at the right end of the
tab, after *Find* / *Add-ins*):

| Button | What it does |
|---|---|
| **EasyFind** | Opens the search window. |
| **Same sender** | Opens the window and immediately searches every message from the sender of the selected message. |
| **Same subject** | Same, with the subject of the selected message (RE:/FW:/FWD:/RV:/TR:… prefixes are ignored). |

The same buttons are on the ribbon of an opened message (**Message** tab). Keyboard: press `Alt`,
then the key tips, `EF` opens EasyFind.

The window stays open next to Outlook; you can keep working in Outlook while a search runs.

## Running a search

1. **Find exactly**: type the text. It is matched literally, anywhere in the field – `1234` finds
   `ABC-1234`, `@acme` finds every address at acme.com, `pay before` finds that phrase. It is not
   case sensitive unless you tick the option. Recent searches are in the drop-down.
2. **Look in**: tick the fields. *Attachment names* is slower because every message with attachments
   in the scope has to be opened.
3. **Where**:
   - *Current folder* – the folder shown in Outlook.
   - *Current folder and its subfolders* (default).
   - *Whole mailbox / data file: …* – one entry per mailbox and PST.
   - *Everything* – all mailboxes and data files.
   - *Choose a folder…* – pick any folder (searched with its subfolders).
   - *Include Deleted Items and Junk* and *Mail only* (untick to also search calendar items,
     contacts, tasks and notes).
4. **Options**: *Case sensitive*, *Whole word*, and a date range (received date).
5. Press **Search** (or Enter). The status line shows the folder being scanned and the number of hits;
   **Stop** (or Esc) ends the search early and keeps what was found so far.

## Working with the results

- Click a column header to sort. Double-click (or Enter) opens the message; several selected messages
  open at once.
- **Show in folder** switches Outlook to the folder and selects the message there.
- Right-click: open, show in folder, copy subject / sender / whole row, and *Search this sender* /
  *Search this subject* for a follow-up search.
- **Export CSV…** writes the list (semicolon separated, opens in Excel).
- **Create Outlook search folder** turns the current search into a permanent Search Folder in the
  folder pane (works for one mailbox / folder scope, not for "Everything"). Outlook keeps it updated.
- **Settings…**: maximum number of results (default 2 000), automatic update check, update server
  address, and a button to open the log file.

## Speed

Subject / From / To / CC / BCC searches are fast (a few seconds even for a whole mailbox). **Body**
search reads the text of every message in the scope and is the slow part: roughly 1–3 seconds per
thousand messages on a local PST or cached mailbox, slower on an Exchange mailbox in online mode. For
big mailboxes start with the folder you expect, or narrow the date range.

## Updates

Once a day, when Outlook starts, EasyFind silently checks the EHTU update server. If a newer version
exists, a red **Update x.y.z available – click to install** link appears in the window header. Click it,
confirm, and the installer downloads and runs: Outlook is closed, the add-in is replaced and Outlook is
started again. You can also check manually in *Settings… → Check now*, or run a newer
`EasyFindSetup-<version>.exe` yourself.

## Uninstalling

Windows *Settings → Apps → EHTU EasyFind for Outlook → Uninstall* (or Control Panel → Programs). The
add-in registration is removed; Outlook must be restarted.
