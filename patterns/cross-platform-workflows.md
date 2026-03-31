# Cross-Platform Workflows

> **Source**: mac heir (MacBook Neo guide) | **Promoted to**: Global Knowledge
> **Scope**: Daily driver patterns for running Windows and macOS side by side

How to run Windows and macOS side by side as a daily driver on both. This covers Microsoft 365, Outlook, Copilot, authentication, browsers, passwords, and the apps that bridge both worlds.

## Microsoft 365 on Mac

Microsoft maintains full-featured native Mac apps for the entire Office suite. They're not watered-down web wrappers -- they're real apps with feature parity for most tasks.

### Install

```bash
brew install --cask microsoft-office
```

This installs Word, Excel, PowerPoint, Outlook, OneNote, and OneDrive in one shot.

Or install individually from the Mac App Store.

### What Works the Same

| Feature                         | Mac                   | Windows             |
| ------------------------------- | --------------------- | ------------------- |
| Core editing (Word, Excel, PPT) | Full feature set      | Full feature set    |
| Real-time co-authoring          | Yes                   | Yes                 |
| OneDrive sync and AutoSave      | Yes                   | Yes                 |
| Microsoft 365 Copilot           | Yes                   | Yes                 |
| Teams meetings and chat         | Yes                   | Yes                 |
| Outlook email and calendar      | Yes                   | Yes                 |
| SharePoint and OneDrive web     | Safari or any browser | Edge or any browser |

### What's Different on Mac

| Feature                  | Mac Behavior                                     | Windows Behavior |
| ------------------------ | ------------------------------------------------ | ---------------- |
| VBA macros               | Supported but some Windows-specific APIs missing | Full support     |
| COM add-ins              | Not supported                                    | Supported        |
| Access database          | Not available on Mac                             | Desktop app      |
| Publisher                | Not available on Mac                             | Desktop app      |
| PowerPivot / Power Query | Limited in desktop Excel                         | Full support     |
| File paths in macros     | Use `/` (POSIX) paths                            | Use `\` paths    |

> If you need Access or Publisher, use the web versions at office.com or use your Windows machine.

### Power Query and Power Pivot

Excel on Mac now supports basic Power Query (Get & Transform Data). For advanced data modeling:

- Simple queries: use Excel on Mac
- Complex Power Query / Power Pivot: use Excel on Windows, or use Power BI Desktop (Windows only)
- Both platforms: save to OneDrive so the file is accessible from either machine

## Outlook on Mac

The new Outlook for Mac is a modern, fast email client that syncs with Exchange, Microsoft 365, Gmail, iCloud Mail, and other providers.

### Setup

1. Open Outlook (installed with Microsoft 365)
2. Sign in with your work or personal Microsoft account
3. Outlook syncs mail, calendar, contacts, and tasks automatically

### Mac Outlook vs Windows Outlook

| Feature                   | Mac     | Windows               |
| ------------------------- | ------- | --------------------- |
| Exchange and M365 mail    | Yes     | Yes                   |
| Gmail and iCloud accounts | Yes     | Yes (new Outlook)     |
| Shared mailboxes          | Yes     | Yes                   |
| Calendar scheduling       | Yes     | Yes                   |
| Focused Inbox             | Yes     | Yes                   |
| Rules and filters         | Yes     | Yes                   |
| Offline access            | Yes     | Yes                   |
| COM add-ins               | No      | Yes (classic Outlook) |
| S/MIME encryption         | Limited | Full support          |
| PST file import           | No      | Yes                   |

### Outlook vs Apple Mail

You don't have to choose -- but here's when each makes sense:

| Use Outlook when...                 | Use Apple Mail when...                  |
| ----------------------------------- | --------------------------------------- |
| Your workplace runs Exchange/M365   | You want deep macOS integration         |
| You need shared calendars at work   | You use iCloud Mail as primary          |
| You want Teams integration in email | You prefer a simpler, lighter client    |
| You manage multiple work accounts   | You want Handoff between Mac and iPhone |

> You can add your Microsoft 365 account to Apple Mail too (System Settings > Internet Accounts > Microsoft Exchange), but Outlook gives you better calendar and Teams integration.

## Microsoft Copilot

Copilot works across both platforms. Here's the landscape:

### Copilot in Microsoft 365 Apps

Available in Word, Excel, PowerPoint, Outlook, and Teams on both Mac and Windows (requires a Copilot license):

- **Word**: Draft documents, summarize, rewrite
- **Excel**: Analyze data, create formulas, generate charts
- **PowerPoint**: Create presentations from prompts or documents
- **Outlook**: Draft replies, summarize email threads
- **Teams**: Meeting summaries, catch-up on missed conversations

Works identically on both platforms.

### Copilot in Edge / Web

[copilot.microsoft.com](https://copilot.microsoft.com) works in any browser on any platform. Same Copilot experience in Safari on Mac as in Edge on Windows.

### GitHub Copilot (for Developers)

Available in VS Code on both Mac and Windows. Same extension, same features:

```bash
# Install VS Code
brew install --cask visual-studio-code
```

Then install the GitHub Copilot extension from the Extensions marketplace. Your subscription and settings sync across platforms via VS Code Settings Sync.

## Authentication and Sign-In

### Touch ID on Mac vs Windows Hello

Both platforms have biometric login, and they integrate with browsers and apps:

| Feature                   | Mac (Touch ID)                      | Windows (Hello)          |
| ------------------------- | ----------------------------------- | ------------------------ |
| Fingerprint login         | Yes (Touch ID sensor)               | Yes (fingerprint reader) |
| Face recognition          | No (Mac doesn't have IR camera)     | Yes (IR camera)          |
| Browser password autofill | Safari, Chrome (with extension)     | Edge, Chrome             |
| Passkey support           | Yes (Safari, system-wide)           | Yes (Edge, system-wide)  |
| `sudo` in Terminal        | `sudo` with Touch ID (configurable) | N/A                      |

### Enabling Touch ID for sudo

Add to `/etc/pam.d/sudo_local`:

```
auth       sufficient     pam_tid.so
```

Now you can approve Terminal `sudo` commands with your fingerprint instead of typing your password.

### Passkeys

Passkeys replace passwords entirely. They sync via iCloud Keychain on Mac/iPhone and via Windows Hello on Windows:

- **On Mac**: Safari and apps support passkeys natively. Stored in iCloud Keychain.
- **On Windows**: Edge and Chrome support passkeys via Windows Hello.
- **Cross-platform**: Some passkey providers (1Password, Bitwarden) sync passkeys across Mac and Windows.

> If you need passkeys on both platforms, use 1Password or Bitwarden as your passkey provider rather than platform-specific storage.

## Passwords Across Platforms

### Option 1: iCloud Passwords on Windows

Apple provides an iCloud Passwords extension for Chrome and Edge on Windows:

1. Install [iCloud for Windows](https://apps.microsoft.com/detail/9PKTQ5699M62)
2. Enable **Passwords** in the iCloud for Windows app
3. Install the iCloud Passwords browser extension in Chrome or Edge
4. Your Safari passwords now autofill on Windows

### Option 2: Cross-Platform Password Manager

| Manager                     | Mac      | Windows                   | Browser                        | Mobile       |
| --------------------------- | -------- | ------------------------- | ------------------------------ | ------------ |
| **Bitwarden**               | Yes      | Yes                       | All browsers                   | iOS, Android |
| **1Password**               | Yes      | Yes                       | All browsers                   | iOS, Android |
| **Apple Passwords**         | Built-in | Via iCloud for Windows    | Safari + Chrome/Edge extension | iOS          |
| **Microsoft Authenticator** | iOS only | Windows Hello integration | Edge                           | iOS, Android |

> Recommendation: If you use both platforms daily, Bitwarden (free) or 1Password (paid) gives you the smoothest experience. If you're mostly on Apple devices with occasional Windows, iCloud Passwords with the Windows extension works fine.

## Browser Sync

### Safari (Mac) to Windows

Safari doesn't exist on Windows, but you can sync bookmarks:

1. Install iCloud for Windows
2. Enable **Bookmarks** sync
3. Choose Chrome or Edge as the target
4. Your Safari bookmarks appear in the Windows browser

### Chrome or Edge (Both Platforms)

The easiest path -- use the same browser on both:

| Browser    | Syncs                                           | How                                    |
| ---------- | ----------------------------------------------- | -------------------------------------- |
| **Chrome** | Bookmarks, history, passwords, tabs, extensions | Sign in with Google account on both    |
| **Edge**   | Bookmarks, history, passwords, tabs, extensions | Sign in with Microsoft account on both |

> If you're in a Microsoft 365 environment, **Edge** gives you the tightest integration: Copilot sidebar, M365 feed, work/personal profiles, and collections.

### Tab Continuity

- **Safari → Safari (Mac to iPhone)**: Automatic via iCloud Tabs
- **Chrome → Chrome**: Open tabs sync via Google account. `Cmd + Shift + T` reopens recent tabs.
- **Edge → Edge**: Same as Chrome. Plus vertical tabs and workspaces.

## Calendar Sync

Your calendar should work everywhere without duplicating events:

### Single Calendar, Multiple Clients

| Calendar Account         | Works In (Mac)             | Works In (Windows)        | Works In (Web)      |
| ------------------------ | -------------------------- | ------------------------- | ------------------- |
| Microsoft 365 / Exchange | Outlook, Apple Calendar    | Outlook                   | outlook.com         |
| Google Calendar          | Apple Calendar, Google web | Outlook (new), Google web | calendar.google.com |
| iCloud Calendar          | Apple Calendar             | iCloud for Windows        | icloud.com          |

### Recommended Setup

1. **Work calendar**: Keep in Microsoft 365 / Exchange. Use Outlook on both platforms.
2. **Personal calendar**: Keep in iCloud (if Apple-first) or Google (if cross-platform).
3. **View all in one place**: Apple Calendar on Mac can show Exchange + iCloud + Google calendars together. Outlook can show Exchange + Google together.

### Adding Exchange to Apple Calendar

System Settings > Internet Accounts > Microsoft Exchange > sign in > enable Calendar

Your work calendar now appears in Apple Calendar alongside your personal calendars.

## Notes and Tasks Across Platforms

### Notes

| App             | Mac      | Windows            | Web               | Mobile       |
| --------------- | -------- | ------------------ | ----------------- | ------------ |
| **Apple Notes** | Built-in | iCloud for Windows | icloud.com        | iOS          |
| **OneNote**     | Yes      | Yes                | onenote.com       | iOS, Android |
| **Notion**      | Yes      | Yes                | notion.so         | iOS, Android |
| **Obsidian**    | Yes      | Yes                | N/A (local files) | iOS, Android |

> For work notes in a Microsoft shop, OneNote integrates with Teams and SharePoint. For personal notes, Apple Notes is excellent on Mac/iPhone but limited on Windows (web-only via icloud.com).

### Tasks and Reminders

| App                 | Mac             | Windows         | Integration             |
| ------------------- | --------------- | --------------- | ----------------------- |
| **Apple Reminders** | Built-in        | icloud.com only | Siri, Apple Calendar    |
| **Microsoft To Do** | Yes (App Store) | Yes             | Outlook, Teams, Planner |
| **Todoist**         | Yes             | Yes             | Everything              |

> If your team uses Microsoft Planner or Teams tasks, install **Microsoft To Do** on your Mac -- it syncs with Planner and shows your Outlook flagged emails as tasks.

## Printing

### Print to PDF

| Platform | How                                                  |
| -------- | ---------------------------------------------------- |
| Mac      | `Cmd + P` > PDF dropdown (bottom-left) > Save as PDF |
| Windows  | `Ctrl + P` > select "Microsoft Print to PDF"         |

Both work in every app. The Mac version is slightly more convenient with the built-in PDF button in every print dialog.

### Shared Printers

See [Mac + PC Networking](mac-pc-networking.md) for sharing printers between your Mac and PC on the same network.

## Notifications

### Getting the Same Notifications on Both Machines

If you use Teams, Outlook, and Slack on both platforms, you'll get duplicate notifications. Solutions:

1. **Turn off email notifications on one device** -- let your primary machine handle it
2. **Use Focus modes on Mac** to silence work notifications after hours
3. **Configure notification priority** in each app's settings independently

### Focus Mode vs Windows Focus

| Feature              | Mac Focus               | Windows Focus           |
| -------------------- | ----------------------- | ----------------------- |
| Schedule-based       | Yes                     | Yes                     |
| App filters          | Yes                     | Yes                     |
| Contact filters      | Yes                     | Limited                 |
| Cross-device sync    | Yes (iPhone, iPad, Mac) | Yes (Windows + Android) |
| Calendar integration | Yes                     | Yes                     |

## Summary: The Recommended Dual-Platform Stack

| Need                   | Mac App                   | Windows App                     | Sync Method            |
| ---------------------- | ------------------------- | ------------------------------- | ---------------------- |
| Email (work)           | Outlook                   | Outlook                         | Microsoft 365          |
| Email (personal)       | Apple Mail or Outlook     | Outlook or web                  | Exchange / IMAP        |
| Calendar               | Outlook or Apple Calendar | Outlook                         | Microsoft 365          |
| Documents              | Microsoft 365 / Pages     | Microsoft 365                   | OneDrive               |
| Notes                  | Apple Notes + OneNote     | OneNote                         | iCloud + Microsoft 365 |
| Tasks                  | Microsoft To Do           | Microsoft To Do                 | Microsoft 365          |
| Passwords              | Bitwarden or iCloud       | Bitwarden or iCloud for Windows | Cloud sync             |
| Browser                | Safari or Edge            | Edge                            | Microsoft account      |
| Cloud files (work)     | OneDrive                  | OneDrive                        | Microsoft 365          |
| Cloud files (personal) | iCloud Drive              | iCloud for Windows              | iCloud                 |
| Chat (work)            | Teams                     | Teams                           | Microsoft 365          |
| Code editor            | VS Code                   | VS Code                         | Settings Sync          |
| AI assistant           | Copilot / GitHub Copilot  | Copilot / GitHub Copilot        | Account-based          |

## Related

- Cloud storage: OneDrive and iCloud harmonization patterns
- Mac + PC networking: file sharing, screen sharing, printers
- Security and privacy: passwords, encryption, and authentication across platforms