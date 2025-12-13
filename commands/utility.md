---
description: Utility commands for everyday use.
icon: wrench
---

# Utility Commands

## Server Aliases

Create command shortcuts for your server.

| Command | Description | Syntax | Permission |
|---------|-------------|--------|------------|
| `alias add` | Add a shortcut alias for a command | `alias add (shortcut) (command)` | `administrator` |
| `alias remove` | Remove a specific alias | `alias remove (shortcut)` | `administrator` |
| `alias removeall` | Remove all aliases for a command | `alias removeall (command)` | `administrator` |
| `alias view` | View what command an alias maps to | `alias view (shortcut)` | `administrator` |
| `alias list` | List all server aliases | `alias list` | `administrator` |
| `alias reset` | Remove all server aliases | `alias reset` | `administrator` |

**Aliases:** `shortcut`

**Example:**
```
,alias add k kick
,alias add b ban @user
```

Now `,k @user` will kick and `,b` will ban the preset user.

{% hint style="info" %}
You can have up to **50 server aliases**.
{% endhint %}

---

## Color

| Command | Description | Aliases | Syntax | Permission |
|---------|-------------|---------|--------|------------|
| `color` | Display color information from hex or name | `colour` | `color (hex/name)` | None |
| `hex` | Get dominant colors from an image | `dominant` | `hex [user/url/attachment]` | None |

**Examples:**
```
,color #ff5733
,color red
,color 255, 87, 51
,hex @user
,hex (with image attachment)
```

---

## Embeds

Create custom embeds and containers.

| Command | Description | Aliases | Syntax | Permission |
|---------|-------------|---------|--------|------------|
| `createembed` | Create a custom embed | `ce` | `createembed (code)` | `manage_messages` |
| `copyembed` | Get embed code from a message | - | `copyembed [message]` | `manage_messages` |

**Example:**
```
,ce {embed}$v{title: Hello}$v{description: World}
,copyembed 123456789012345678
```

{% hint style="info" %}
See the [Embed Builder Guide](../setup-guides/embeds.md) for detailed syntax.
{% endhint %}

---

## Reminders

Set personal reminders.

| Command | Description | Syntax | Permission |
|---------|-------------|--------|------------|
| `remind` | Set a reminder | `remind (duration) (reminder)` | None |
| `remind add` | Set a reminder | `remind add (duration) (reminder)` | None |
| `remind remove` | Remove a reminder | `remind remove (id)` | None |
| `remind list` | List all your reminders | `remind list` | None |

**Duration Format:** `1m`, `1h`, `1d`, `1w`

**Examples:**
```
,remind 1h check the oven
,remind 30m take a break
,remind list
,remind remove 1
```

{% hint style="info" %}
- Minimum duration: **1 minute**
- Maximum duration: **100 years**
- Maximum reminders: **25**
{% endhint %}

---

## Transcribe

Transcribe audio or video files to text.

| Command | Description | Aliases | Syntax | Permission |
|---------|-------------|---------|--------|------------|
| `transcribe` | Transcribe audio/video to text | `transcript`, `ts` | `transcribe [url/attachment/reply]` | None |

**Usage:**
- Attach an audio/video file and run `,transcribe`
- Provide a URL: `,transcribe https://example.com/audio.mp3`
- Reply to a voice message and run `,transcribe`

**Supported Formats:** MP3, WAV, OGG, M4A, FLAC, AAC, OPUS, WEBM, MP4, MOV, AVI, MKV

**Examples:**
```
,transcribe https://example.com/audio.mp3
,ts (with audio attachment)
,transcript (reply to a voice message)
```

{% hint style="info" %}
The transcription is sent as plain text without any embed formatting.
{% endhint %}
