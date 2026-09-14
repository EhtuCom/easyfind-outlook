# Troubleshooting

Log file: `%LOCALAPPDATA%\EHTU\EasyFind\easyfind.log` (button *Open log file* in *Settings…*). Every
search is logged with its scope, folder count and the exact restriction sent to Outlook; folders
that could not be searched are listed as warnings.

## The EHTU EasyFind group does not appear in the ribbon

| Check | Fix |
|---|---|
| *File → Options → Add-ins*: is *EHTU EasyFind* under **Inactive** or **Disabled** application add-ins? | *Manage: COM Add-ins → Go* and tick it; or *Manage: Disabled Items → Go* and enable it. Then restart Outlook. Running the installer again also re-enables it. |
| Outlook shows "This add-in caused Outlook to start slowly" and disabled it | Click *Always enable this add-in*. EasyFind loads in well under a second; the warning usually comes from a slow first start after installation. |
| The "new Outlook" toggle is on | Switch it off (top right of Outlook). The new Outlook cannot run mailbox add-ins. |
| Installed by a different Windows user | The registration is per user: run the setup as the user who uses Outlook. |
| Corporate policy blocks COM add-ins | Group policy *Block all unmanaged add-ins* / *List of managed add-ins*: the administrator must allow ProgID `EHTU.EasyFind`. |
| Log says `OnConnection failed` | Send the log to support. |

## Searches

| Symptom | Cause / fix |
|---|---|
| Nothing found although the message exists | Is the scope right (current folder vs. whole mailbox)? Is the text really in one of the ticked fields? For recipients only the display names are searched unless *Case sensitive* / *Whole word* is on (then addresses are checked too); use *From* with the address for senders. |
| "Folder … does not support this search" in the log | Some stores (SharePoint lists, some IMAP folders, archive mailboxes in online mode) reject text restrictions on the body. Untick *Body* for those, or search them with Outlook's own search. |
| Body search is very slow | It reads every message in the scope. Narrow the scope or the date range, or untick *Body* first to see whether subject/sender searches already give the answer. |
| Result limit reached | Raise the limit in *Settings…* or narrow the search. |
| "Show in folder" does nothing | The folder is in a store that is not shown in the folder pane (archive not mounted) or the item was moved since the search. Run the search again. |
| Search folder cannot be created | Outlook search folders live inside one mailbox; choose one mailbox or a folder as scope, not *Everything*. Exchange also limits the number of search folders. |

## Updates

| Symptom | Cause / fix |
|---|---|
| "Update check skipped" in the log | No network, or `version.json` not published yet (HTTP 404). Harmless. |
| Update banner keeps appearing | Click it and choose *Skip this version*, or install the update. |
| Installer says files are in use | Close Outlook (and any other program that loaded EasyFind.dll, e.g. a second Outlook profile session), then run the installer again. |

## Removing everything

Uninstall from Windows Settings; then delete `%APPDATA%\EHTU\EasyFind` (settings) and
`%LOCALAPPDATA%\EHTU\EasyFind` (log) if you want no traces left.
