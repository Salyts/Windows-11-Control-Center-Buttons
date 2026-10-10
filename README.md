# Windows 11 Control Center Buttons

• **[Report a bug or suggest a feature](https://github.com/Salyts/Windows-11-Control-Center-Buttons/issues)** · **[Discussion on Discord](https://discord.com/channels/923944342991818753/1558419938820227123)** · **[Support](https://ko-fi.com/salyts)**

Removes the stock **Settings (gear)** button from the bottom bar of the Windows 11 Control Center panel and puts your own buttons there instead.

Actions are run by a dedicated Windhawk tool-mod process (`windhawk.exe -tool-mod`), the panel host sends the click to a tiny hidden window inside that process, which runs the command.

| Before | After |
|--------|---------|
| ![before](https://i.imgur.com/ILoCB2R.png) | ![after](https://i.imgur.com/R7ET89k.png) |

## Button fields

| Field | Description |
|---|---|
| **Preset** | Ready-made button. Set `Custom` to define your own. |
| **Name** | Tooltip. Empty on presets = default name. |
| **Icon** | Segoe Fluent glyph (`E713` or `\uE713`), image path (PNG/ICO/JPG/BMP/WEBP) or `.exe`/`.dll` path to take the icon from. |
| **Action** | Used for `Custom`. One or several commands, run in order. |
| **Left-click submenu** | Menu opened on left click (replaces Action). |
| **Right-click submenu** | Menu opened on right click. |

## Action formats

| Prefix | Example | Description |
|--------|---------|-------------|
| `" "` | `"C:\Program Files\Windhawk\windhawk.exe"` | Opens a file or folder by absolute path. |
| `~` | `~Downloads` or `~windhawk.exe` | Opens a folder or file by name. |
| `cmd:` | `cmd:control` | Runs a command through `cmd.exe`. |
| `ps:` or `powershell:` | `ps:shutdown /r /f /t 0` | Runs through `powershell.exe` |
| `press:` | `press:Win+E` or `press:0x5B;0x45` | Keyboard key press using [Win32 key code](https://learn.microsoft.com/en-us/windows/win32/inputdev/virtual-key-codes). |
| `web:` | `web:https://windhawk.net/` | Opens a URL in the default browser. |
| `ms-settings:` | `ms-settings:bluetooth` | Opens a Windows Settings page. |

### Modifier signs (prepend to any action)
| Sign | Example | Description |
|------|---------|-------------|
| `-` | `-"C:\Program Files\app.exe"` or `-ps:shutdown /r /f /t 0` | Runs as administrator. |
| `*` | `*cmd:tasklist` or `*ps:Get-Process` | Execution with a terminal window. (only for `cmd:` and `ps:` prefixes). |

Signs can be combined: `-*cmd:tasklist` runs cmd in a visible window as admin.
