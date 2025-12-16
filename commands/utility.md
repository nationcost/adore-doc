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

---

## Steal

Quickly steal emojis and stickers from messages.

| Command | Description | Aliases | Syntax | Permission |
|---------|-------------|---------|--------|------------|
| `steal` | Steal emojis or stickers | `yoink` | `steal [emojis...]` or reply to message | `manage_emojis` |

**Usage:**
- Reply to a message containing emojis/stickers and run `,steal`
- Provide emojis directly: `,steal :emoji1: :emoji2:`

**Examples:**
```
,steal :pepe: :sadge:
,yoink (reply to a message)
```

{% hint style="info" %}
This command steals both **emojis** and **stickers** from replied messages.
{% endhint %}

---

## Emoji Management

Manage your server's custom emojis.

| Command | Description | Syntax | Permission |
|---------|-------------|--------|------------|
| `emoji add` | Add emojis to the server | `emoji add (emojis...)` | `manage_emojis` |
| `emoji remove` | Remove emojis from the server | `emoji remove (emojis...)` | `manage_emojis` |
| `emoji list` | List all server emojis | `emoji list` | None |

**Examples:**
```
,emoji add :pepe: :sadge: :kekw:
,emoji remove :pepe:
,emoji list
```

{% hint style="info" %}
The emoji list displays with numbered entries, emoji preview, and clickable links to the emoji URL.
{% endhint %}

---

## Sticker Management

Manage your server's custom stickers.

| Command | Description | Syntax | Permission |
|---------|-------------|--------|------------|
| `sticker add` | Add a sticker from a message link | `sticker add (message link)` | `manage_emojis` |
| `sticker remove` | Remove a sticker by link or name | `sticker remove (message link or name)` | `manage_emojis` |
| `sticker list` | List all server stickers | `sticker list` | None |

**Examples:**
```
,sticker add https://discord.com/channels/123/456/789
,sticker remove https://discord.com/channels/123/456/789
,sticker remove MyStickerName
,sticker list
```

{% hint style="info" %}
Provide a **message link** containing the sticker you want to add or remove.
{% endhint %}

---

## Name History

Track username and nickname changes.

| Command | Description | Aliases | Syntax | Permission |
|---------|-------------|---------|--------|------------|
| `namehistory` | View name history for a user | `nh`, `names` | `namehistory [user]` | None |
| `clearhistory` | Clear your name history | `clearnames` | `clearhistory` | None |

**Display Format:**
- `1N` = Nickname change
- `2U` = Username change

**Examples:**
```
,namehistory @user
,nh
,clearhistory
```

{% hint style="info" %}
Name history is automatically tracked when users change their username or nickname. The bot also sends notifications to a designated channel when usernames become available.
{% endhint %}

---

## Notes

Manage your personal notes.

| Command | Description | Syntax | Permission |
|---------|-------------|--------|------------|
| `note` | View your notes | `note` | None |
| `note add` | Add a personal note | `note add (text)` | None |
| `note remove` | Remove a note by ID | `note remove (id)` | None |
| `note list` | List all your notes | `note list` | None |
| `note reset` | Delete all your notes | `note reset` | None |

**Examples:**
```
,note add remember to buy milk
,note remove 1
,note list
,note reset
```

{% hint style="info" %}
- Maximum **50 notes** per user
- Maximum **500 characters** per note
{% endhint %}

---

## Repost

Download videos from social media platforms.

| Command | Description | Aliases | Syntax | Permission |
|---------|-------------|---------|--------|------------|
| `repost` | Download videos from Instagram, TikTok, or YouTube | `rp` | `repost (url)` | None |

**Supported Platforms:**
- Instagram (posts, reels, TV)
- TikTok
- YouTube (videos, shorts)

**Examples:**
```
,repost https://www.instagram.com/reel/...
,rp https://www.tiktok.com/@user/video/...
,repost https://youtu.be/...
```

**Alternative:** You can also use `adore {link}` in chat to auto-download.

{% hint style="info" %}
- Maximum file size: **25MB**
- YouTube max duration: **10 minutes**
{% endhint %}

---

## Music

Play music in voice channels with autoplay and 24/7 support.

| Command | Description | Aliases | Syntax | Permission |
|---------|-------------|---------|--------|------------|
| `play` | Play a song from SoundCloud or URL | `p` | `play (query or url)` | None |
| `pause` | Pause the current track | - | `pause` | None |
| `resume` | Resume the paused track | `unpause` | `resume` | None |
| `skip` | Skip to the next track | `s`, `next` | `skip` | None |
| `stop` | Stop playback and disconnect | `dc`, `disconnect`, `leave` | `stop` | None |
| `nowplaying` | Show the currently playing track | `np`, `current` | `nowplaying` | None |
| `queue` | Show the current queue | `q` | `queue` | None |
| `volume` | Set the player volume | `vol`, `v` | `volume [0-100]` | None |
| `autoplay` | Toggle autoplay similar tracks | `ap` | `autoplay` | None |
| `stay` | Toggle 24/7 mode | `247`, `24/7` | `stay` | None |

**Examples:**
```
,play never gonna give you up
,play https://soundcloud.com/artist/track
,np
,skip
,volume 50
,autoplay
,stay
```

**Features:**
- Interactive buttons on play/nowplaying messages (pause, play, stop)
- Autoplay mode plays similar tracks when queue ends
- 24/7 mode keeps the bot in voice channel even when users leave
- Progress bar display in nowplaying command

{% hint style="info" %}
- Autoplay searches for similar tracks based on the current track's artist and title
- 24/7 mode persists until disabled or bot is stopped
- Volume range: **0-100%**
{% endhint %}

---

## AFK

Set your AFK status across all servers.

| Command | Description | Syntax | Permission |
|---------|-------------|--------|------------|
| `afk` | Set your AFK status | `afk [reason]` | None |
| `afk mentions` | View who mentioned you while AFK | `afk mentions` | None |

**Examples:**
```
,afk
,afk sleeping
,afk be back in 30 mins
,afk mentions
```

{% hint style="info" %}
- When someone mentions you while AFK, they'll see your AFK reason and when you went AFK
- Your AFK status is automatically removed when you send a message
- AFK status is **global** (works across all servers)
- Maximum reason length: **200 characters**
- Up to **50 mentions** are tracked
{% endhint %}
