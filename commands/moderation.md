---
description: Moderation commands to keep your server safe and organized.
icon: shield-halved
---

# Moderation Commands

{% hint style="warning" %}
Before using moderation commands, run `,setup` and `,setupmute` to configure the required roles and channels.
{% endhint %}

## Banning

| Command | Description | Aliases | Syntax | Permission |
|---------|-------------|---------|--------|------------|
| `ban` | Ban a user from the server | `deport` | `ban (user) [reason]` | `ban_members` |
| `unban` | Unban a user from the server | - | `unban (user) [reason]` | `ban_members` |
| `softban` | Ban and immediately unban (clears messages) | - | `softban (user) [delete_days] [reason]` | `ban_members` |

**Examples:**
```
,ban @user breaking rules
,ban 123456789012345678 spam
,softban @user 7d flooding chat
,unban 123456789012345678
```

{% hint style="info" %}
**Hackban:** You can ban users who aren't in the server by using their user ID.
{% endhint %}

---

## Kicking

| Command | Description | Aliases | Syntax | Permission |
|---------|-------------|---------|--------|------------|
| `kick` | Kick a member from the server | `boot` | `kick (user) [reason]` | `kick_members` |

**Example:**
```
,kick @user breaking rules
```

---

## Muting

### Text Mute
| Command | Description | Aliases | Syntax | Permission |
|---------|-------------|---------|--------|------------|
| `mute` | Mute a member (prevents typing and reactions) | `sybau` | `mute (user) [duration] [reason]` | `manage_messages` |
| `unmute` | Unmute a member | - | `unmute (user)` | `manage_messages` |

### Image Mute
| Command | Description | Syntax | Permission |
|---------|-------------|--------|------------|
| `imute` | Prevent a member from sending attachments/embeds | `imute (user) [duration] [reason]` | `manage_messages` |
| `iunmute` | Remove image mute from a member | `iunmute (user)` | `manage_messages` |

### Reaction Mute
| Command | Description | Syntax | Permission |
|---------|-------------|--------|------------|
| `rmute` | Prevent a member from adding reactions/stickers | `rmute (user) [duration] [reason]` | `manage_messages` |
| `runmute` | Remove reaction mute from a member | `runmute (user)` | `manage_messages` |

**Duration Format:** `1h`, `30m`, `1d`, `2w`

**Examples:**
```
,mute @user 1h spamming
,imute @user 2d inappropriate images
,rmute @user
```

---

## Timeout

Discord's native timeout feature.

| Command | Description | Aliases | Syntax | Permission |
|---------|-------------|---------|--------|------------|
| `timeout` | Timeout a member | `to` | `timeout (user) (duration) [reason]` | `moderate_members` |
| `untimeout` | Remove timeout from a member | `uto` | `untimeout (user)` | `moderate_members` |

**Example:**
```
,timeout @user 1h spamming
,to @user 30m
```

{% hint style="info" %}
Maximum timeout duration is **28 days**.
{% endhint %}

---

## Jail

Jail removes all roles from a member and restricts them to a jail channel.

| Command | Description | Syntax | Permission |
|---------|-------------|--------|------------|
| `jail` | Jail a member | `jail (user) [duration] [reason]` | `manage_roles` |
| `unjail` | Unjail a member (restores roles) | `unjail (user)` | `manage_roles` |

**Example:**
```
,jail @user 1h breaking rules
,unjail @user
```

{% hint style="warning" %}
Run `,setup` first to create the jail role and channel.
{% endhint %}

---

## Warnings

| Command | Description | Aliases | Syntax | Permission |
|---------|-------------|---------|--------|------------|
| `warn` | Warn a member | - | `warn (user) [reason]` | `manage_messages` |
| `warnings` | View warnings for a member | `warns` | `warnings (user)` | `manage_messages` |
| `clearwarns` | Clear all warnings for a member | - | `clearwarns (user)` | `manage_messages` |

**Example:**
```
,warn @user first warning
,warnings @user
,clearwarns @user
```

---

## Channel Management

| Command | Description | Syntax | Permission |
|---------|-------------|--------|------------|
| `lock` | Lock a channel | `lock [channel]` | `manage_channels` |
| `unlock` | Unlock a channel | `unlock [channel]` | `manage_channels` |
| `hide` | Hide a channel from members | `hide [channel]` | `manage_channels` |
| `unhide` | Unhide a channel | `unhide [channel]` | `manage_channels` |
| `lockall` | Lock all text channels | `lockall` | `manage_guild` |
| `unlockall` | Unlock all text channels | `unlockall` | `manage_guild` |
| `slowmode` | Set slowmode for a channel | `slowmode (on/off) (seconds) [channel]` | `manage_channels` |
| `topic` | Change channel topic | `topic (topic)` | `manage_channels` |

**Examples:**
```
,lock #general
,slowmode on 5
,lockall
```

---

## Moderation History

| Command | Description | Aliases | Syntax | Permission |
|---------|-------------|---------|--------|------------|
| `history` | View punishment history for a member | - | `history (member) [action]` | `manage_messages` |
| `history view` | View details of a specific case | - | `history view (case_id)` | `manage_messages` |
| `history remove` | Remove a case from history | - | `history remove (case_id)` | `administrator` |
| `history removeall` | Remove all cases for a member | - | `history removeall (member)` | `administrator` |
| `modstats` | View moderation statistics | - | `modstats [moderator]` | `manage_messages` |
| `modhistory` | View a moderator's action history | `mhistory` | `modhistory (moderator)` | `manage_messages` |
| `reason` | Update the reason for a case | - | `reason [case_id] (reason)` | `manage_messages` |

**Examples:**
```
,history @user
,history @user warn
,history view 28
,reason 28 updated reason
,modstats @moderator
```

---

## Setup Commands

| Command | Description | Syntax | Permission |
|---------|-------------|--------|------------|
| `setup` | Setup jail role and mod-log channel | `setup` | `administrator` |
| `setupmute` | Setup mute roles (muted, imuted, rmuted) | `setupmute` | `administrator` |

{% hint style="success" %}
Run these commands once when you first add the bot to your server.
{% endhint %}

---

## Nuke

Clone and delete channels, with optional scheduling.

| Command | Description | Syntax | Permission |
|---------|-------------|--------|------------|
| `nuke` | Clone and delete a channel | `nuke [channel]` | `manage_channels` |
| `nuke add` | Schedule a nuke for a channel | `nuke add (interval) [channel] [message]` | `manage_channels` |
| `nuke remove` | Remove a scheduled nuke | `nuke remove [channel]` | `manage_channels` |
| `nuke list` | View all scheduled nukes | `nuke list` | `manage_channels` |
| `nuke view` | View scheduled nuke details | `nuke view [channel]` | `manage_channels` |

**Interval Format:** `1h`, `30m`, `1d`, `12h30m`

**Examples:**
```
,nuke #spam
,nuke add 24h #daily-reset Channel has been reset!
,nuke list
,nuke remove #daily-reset
```

{% hint style="info" %}
- Minimum interval: **1 hour**
- Maximum interval: **30 days**
- Maximum scheduled nukes: **10 per server**
- Channel settings (welcomes, leaves, boosts, logs) are automatically migrated to the new channel
{% endhint %}
