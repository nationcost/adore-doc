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
