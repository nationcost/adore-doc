---
description: Commands to get information about users, the bot, and more.
icon: circle-info
---

# Information Commands

## Bot Information

| Command | Description | Aliases | Syntax |
|---------|-------------|---------|--------|
| `help` | View help for a command or list all commands | `h`, `commands` | `help [command]` |
| `ping` | Check the bot's current latency | `latency`, `ms` | `ping` |
| `uptime` | Check how long the bot has been online | - | `uptime` |

---

## User Information

### Avatar Commands

| Command | Description | Aliases | Syntax |
|---------|-------------|---------|--------|
| `avatar` | View a user's avatar | `av`, `pfp` | `avatar [user]` |
| `serveravatar` | View a user's server-specific avatar | `sav`, `spfp` | `serveravatar [user]` |
| `banner` | View a user's banner | - | `banner [user]` |
| `serverbanner` | View a user's server banner | `sbanner` | `serverbanner [user]` |

**Examples:**
```
,avatar @user
,av 123456789012345678
,banner
```

{% hint style="info" %}
Leave the user argument empty to view your own avatar/banner.
{% endhint %}

---

### User Lookup

| Command | Description | Aliases | Syntax |
|---------|-------------|---------|--------|
| `whois` | View detailed information about a user | `ui`, `userinfo` | `whois [user]` |
| `ask` | Ask Adore a question about the bot (Donator) | - | `ask (question)` |

**What it shows:**
- Display name and username
- Account creation date
- Server join date
- Roles
- Badges (Staff, Donator)
- Mutual servers

**Example:**
```
,whois @user
,ui 123456789012345678
```

---

## Server Information

| Command | Description | Aliases | Syntax |
|---------|-------------|---------|--------|
| `serverinfo` | View detailed information about the server | `si`, `guildinfo` | `serverinfo` |
| `membercount` | View the server's member count | `mc` | `membercount` |
| `roleinfo` | View information about a role | `ri` | `roleinfo (role)` |
| `channelinfo` | View information about a channel | `ci` | `channelinfo [channel]` |

### Member Count

Shows the server's member statistics with:
- Total users
- Human members
- Bot accounts
- Members joined today (in footer)

**Example:**
```
,membercount
,mc
```

### Server Info

Shows comprehensive server information including:
- Owner and server ID
- Creation date
- Member counts
- Channel counts
- Roles, emojis, stickers
- Boost level and count
- Verification level

**Example:**
```
,serverinfo
,si
```

### Role Info

Shows detailed information about a role:
- Role ID and color
- Position in hierarchy
- Properties (hoisted, mentionable, managed)
- Member count
- Key permissions

**Example:**
```
,roleinfo @Members
,ri @Admin
```

### Channel Info

Shows information about a channel:
- Channel ID and type
- Category
- NSFW status
- Slowmode (for text channels)
- Bitrate and user limit (for voice channels)

**Example:**
```
,channelinfo #general
,ci
```
