---
description: Guide to setting up moderation commands in your server.
icon: hammer
---

# Moderation Setup

## Overview

Before using moderation commands, you need to set up the required roles and channels. This is a one-time setup.

---

## Quick Setup

Run these two commands to set up everything:

```
,setup
,setupmute
```

---

## What `,setup` Creates

The setup command creates:

### 1. Jailed Role
- Name: `jailed`
- Permissions: Cannot view any channels except the jail channel
- Used by: `jail` and `unjail` commands

### 2. Jailed Channel
- Name: `#jailed`
- Only visible to jailed members and staff
- Jailed members can send messages here

### 3. Mod-Log Channel
- Name: `#mod-log`
- Logs all moderation actions
- Only visible to staff

---

## What `,setupmute` Creates

The setupmute command creates three mute roles:

### 1. Muted Role
- Name: `muted`
- Cannot send messages
- Cannot add reactions
- Cannot speak in voice
- Used by: `mute` and `unmute` commands

### 2. Image Muted Role
- Name: `imuted`
- Cannot attach files
- Cannot embed links
- Used by: `imute` and `iunmute` commands

### 3. Reaction Muted Role
- Name: `rmuted`
- Cannot add reactions
- Cannot use external emojis
- Cannot use stickers
- Used by: `rmute` and `runmute` commands

---

## Manual Setup

If you prefer to set things up manually:

### Creating the Jail Role

1. Create a role named exactly `jailed`
2. Set the role color (optional)
3. For each channel, deny the `View Channel` permission for this role
4. Create a `#jailed` channel
5. In `#jailed`, allow the `jailed` role to view and send messages

### Creating Mute Roles

1. Create roles named exactly `muted`, `imuted`, and `rmuted`
2. For each channel, set the appropriate permission overwrites:

**For `muted`:**
- Send Messages: ❌
- Add Reactions: ❌
- Speak: ❌

**For `imuted`:**
- Attach Files: ❌
- Embed Links: ❌

**For `rmuted`:**
- Add Reactions: ❌
- Use External Emojis: ❌
- Use External Stickers: ❌

---

## Mod-Log

All moderation actions are automatically logged to the `#mod-log` channel:

- Bans / Unbans
- Kicks
- Mutes / Unmutes
- Timeouts
- Jails / Unjails
- Warnings

Each log entry includes:
- Action type
- Target user
- Moderator
- Reason
- Duration (if applicable)
- Case ID

---

## Permissions Required

Make sure the bot has these permissions:

| Permission | Required For |
|------------|--------------|
| `Ban Members` | ban, unban, softban |
| `Kick Members` | kick |
| `Manage Roles` | mute, jail, autorole |
| `Manage Channels` | lock, hide, setup |
| `Moderate Members` | timeout |
| `Manage Messages` | warn, slowmode |
| `View Audit Log` | logging |

---

## Troubleshooting

### "Role not found" Error

Make sure you've run `,setup` or `,setupmute` first.

### Bot Can't Assign Roles

The bot's role must be **higher** than the roles it's trying to assign. Drag the bot's role above the mute/jail roles in Server Settings > Roles.

### Mute Not Working in Some Channels

Run `,setupmute` again to update permissions for new channels, or manually set the permissions for the mute roles in those channels.

### Jail Channel Visible to Everyone

Check that the `#jailed` channel has:
- `@everyone`: View Channel ❌
- `jailed`: View Channel ✅

---

## Best Practices

{% hint style="success" %}
**Role Hierarchy:** Keep the bot's role near the top of your role list so it can manage most roles.
{% endhint %}

{% hint style="info" %}
**Mod-Log Access:** Only give trusted staff access to the mod-log channel.
{% endhint %}

{% hint style="warning" %}
**New Channels:** When you create new channels, run `,setupmute` again to apply mute permissions.
{% endhint %}
