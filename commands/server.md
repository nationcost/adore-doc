---
description: Commands to manage and configure your server.
icon: server
---

# Server Management Commands

## Prefix

| Command | Description | Aliases | Syntax | Permission |
|---------|-------------|---------|--------|------------|
| `prefix` | View the current prefix | - | `prefix` | None |
| `prefix set` | Set a custom prefix for the server | - | `prefix set (prefix)` | `administrator` |
| `prefix remove` | Reset the prefix to default | `reset` | `prefix remove` | `administrator` |

**Example:**
```
,prefix set !
!prefix remove
```

{% hint style="info" %}
The default prefix is `,` — Maximum prefix length is **3 characters**.
{% endhint %}

---

## Server Overview

| Command | Description | Aliases | Syntax | Permission |
|---------|-------------|---------|--------|------------|
| `overview` | View server configuration overview | `ov` | `overview` | None |

Shows:
- Current prefix
- Moderation system status
- Mute system status
- Server owner
- Fake owner (if set)

---

## Settings

| Command | Description | Syntax | Permission |
|---------|-------------|--------|------------|
| `settings fakeowner` | Set or remove a fake owner | `settings fakeowner (user)` | `server_owner` |

**Fake Owner:** A user who has owner-level permissions for bot commands without being the actual server owner.

**Example:**
```
,settings fakeowner @trusted_admin
,settings fakeowner  (leave empty to remove)
```

{% hint style="warning" %}
Only the actual server owner can set a fake owner.
{% endhint %}

---

## Autorole

Automatically assign roles to new members when they join.

| Command | Description | Syntax | Permission |
|---------|-------------|--------|------------|
| `autorole add` | Add a role to autoroles | `autorole add (role)` | `administrator` |
| `autorole remove` | Remove a role from autoroles | `autorole remove (role)` | `administrator` |
| `autorole list` | List all autoroles | `autorole list` | `administrator` |
| `autorole reset` | Remove all autoroles | `autorole reset` | `administrator` |

**Example:**
```
,autorole add @Member
,autorole add @Unverified
,autorole list
```

{% hint style="info" %}
You can have up to **10 autoroles**.
{% endhint %}

---

## Role Management

### Basic Role Commands

| Command | Description | Syntax | Permission |
|---------|-------------|--------|------------|
| `role` | Toggle a role on a member | `role (user) (role)` | `manage_roles` |
| `role add` | Add a role to a member | `role add (user) (role)` | `manage_roles` |
| `role has` | View members with a specific role | `role has (role)` | `manage_roles` |

### Mass Role Operations

| Command | Description | Syntax | Permission |
|---------|-------------|--------|------------|
| `role has add` | Add a role to all members with a specific role | `role has add (has_role) (give_role)` | `administrator` |
| `role has remove` | Remove a role from all members with a specific role | `role has remove (has_role) (remove_role)` | `administrator` |
| `role humans` | Add a role to all human members | `role humans (role)` | `administrator` |
| `role bots` | Add a role to all bot members | `role bots (role)` | `administrator` |
| `role cancel` | Cancel a pending mass role operation | `role cancel` | `manage_roles` |

### Role Editing

| Command | Description | Syntax | Permission |
|---------|-------------|--------|------------|
| `role create` | Create a new role | `role create (name)` | `manage_roles` |
| `role delete` | Delete a role | `role delete (role)` | `manage_roles` |
| `role color` | Change a role's color | `role color (role) (hex)` | `manage_roles` |
| `role icon` | Change a role's icon | `role icon (role) (emoji/url)` | `manage_roles` |
| `role rename` | Rename a role | `role rename (role) (new name)` | `manage_roles` |
| `role restore` | Restore roles for a rejoined member | `role restore (member)` | `manage_roles` |

**Examples:**
```
,role @user @Member
,role has add @Member @Verified
,role humans @Human
,role create VIP
,role color @VIP #ff5733
```

{% hint style="info" %}
Mass role operations can be cancelled with `,role cancel` if they're taking too long.
{% endhint %}

---

## Welcome Messages

Send custom messages when members join.

| Command | Description | Syntax | Permission |
|---------|-------------|--------|------------|
| `welcome add` | Add a welcome message to a channel | `welcome add (channel) (message)` | `manage_guild` |
| `welcome remove` | Remove a welcome message | `welcome remove (channel)` | `manage_guild` |
| `welcome list` | List all welcome messages | `welcome list` | `manage_guild` |
| `welcome view` | Preview a welcome message | `welcome view (channel)` | `manage_guild` |

**Example:**
```
,welcome add #welcome Welcome {user.mention} to {guild.name}!
```

---

## Leave Messages

Send custom messages when members leave.

| Command | Description | Syntax | Permission |
|---------|-------------|--------|------------|
| `leave add` | Add a leave message to a channel | `leave add (channel) (message)` | `manage_guild` |
| `leave remove` | Remove a leave message | `leave remove (channel)` | `manage_guild` |
| `leave list` | List all leave messages | `leave list` | `manage_guild` |
| `leave view` | Preview a leave message | `leave view (channel)` | `manage_guild` |

**Example:**
```
,leave add #goodbye {user.name} has left the server.
```

---

## Boost Messages

Send custom messages when members boost the server.

| Command | Description | Syntax | Permission |
|---------|-------------|--------|------------|
| `boost add` | Add a boost message to a channel | `boost add (channel) (message)` | `manage_guild` |
| `boost remove` | Remove a boost message | `boost remove (channel)` | `manage_guild` |
| `boost list` | List all boost messages | `boost list` | `manage_guild` |
| `boost view` | Preview a boost message | `boost view (channel)` | `manage_guild` |

**Example:**
```
,boost add #boosts Thank you {user.mention} for boosting! 🎉
```

### Boost Award Role

Automatically give a role to members who boost the server.

| Command | Description | Syntax | Permission |
|---------|-------------|--------|------------|
| `boost award set` | Set the role to award to boosters | `boost award set (role)` | `manage_guild` |
| `boost award view` | View the current boost award role | `boost award view` | `manage_guild` |
| `boost award unset` | Remove the boost award role | `boost award unset` | `manage_guild` |

**Example:**
```
,boost award set @Booster
,boost award view
,boost award unset
```

{% hint style="info" %}
You can have up to **10 messages** for each type (welcome, leave, boost).
Only **one** award role can be set at a time.
{% endhint %}

---

## Autoreact

Automatically react to messages containing specific trigger words.

| Command | Description | Syntax | Permission |
|---------|-------------|--------|------------|
| `autoreact add` | Add an emoji reaction to a trigger | `autoreact add (emoji) (trigger)` | `manage_guild` |
| `autoreact remove` | Remove an emoji from a trigger | `autoreact remove (emoji) (trigger)` | `manage_guild` |
| `autoreact deleteall` | Delete all reactions for a trigger | `autoreact deleteall (trigger)` | `manage_guild` |
| `autoreact list` | List all autoreacts | `autoreact list` | `manage_guild` |
| `autoreact reset` | Remove all autoreacts | `autoreact reset` | `manage_guild` |

**Example:**
```
,autoreact add 👍 good morning
,autoreact add ❤️ love
```

{% hint style="info" %}
- Up to **5 reactions** per trigger
- Up to **100 triggers** total
{% endhint %}

---

## Autoresponder

Automatically respond to messages containing specific triggers.

| Command | Description | Syntax | Permission |
|---------|-------------|--------|------------|
| `autoresponder add` | Add an autoresponse | `autoresponder add (trigger), (response)` | `manage_guild` |
| `autoresponder remove` | Remove an autoresponse | `autoresponder remove (trigger)` | `manage_guild` |
| `autoresponder list` | List all autoresponders | `autoresponder list` | `manage_guild` |
| `autoresponder view` | Preview an autoresponse | `autoresponder view (trigger)` | `manage_guild` |
| `autoresponder reset` | Remove all autoresponders | `autoresponder reset` | `manage_guild` |

**Aliases:** `ar`

**Example:**
```
,ar add hello, Hello {user.mention}! Welcome to the server.
,ar add ping, Pong! 🏓
```

**Flags:**
- `--reply` - Reply to the message
- `--not_strict` - Match anywhere in message (not exact)
- `--delete N` - Delete response after N seconds (1-10)

**Example with flags:**
```
,ar add hello, Hello there! --reply --delete 5
```

{% hint style="info" %}
You can have up to **100 autoresponders**.
{% endhint %}

---

## Channel Reactions

Automatically react to all messages in specific channels.

| Command | Description | Syntax | Permission |
|---------|-------------|--------|------------|
| `reaction add` | Add reactions to a channel | `reaction add (channel) (emojis...)` | `manage_guild` |
| `reaction remove` | Remove reactions from a channel | `reaction remove (channel)` | `manage_guild` |
| `reaction list` | List all channel reactions | `reaction list` | `manage_guild` |
| `reaction reset` | Remove all channel reactions | `reaction reset` | `manage_guild` |

**Example:**
```
,reaction add #media 👍 👎 ❤️
```

{% hint style="info" %}
Up to **3 reactions** per channel. Slowmode is automatically set to 3 seconds.
{% endhint %}

---

## Button Roles

Add interactive buttons to messages that give/remove roles when clicked.

| Command | Description | Syntax | Permission |
|---------|-------------|--------|------------|
| `buttonrole add` | Add a button role to a message | `buttonrole add (message link) (style) (emote) (name) (role)` | `manage_roles` |
| `buttonrole remove` | Remove a button role | `buttonrole remove (message link) (role)` | `manage_roles` |
| `buttonrole removeall` | Remove all button roles from a message | `buttonrole removeall (message link)` | `manage_roles` |
| `buttonrole list` | List all button roles | `buttonrole list` | `manage_roles` |
| `buttonrole reset` | Remove all button roles | `buttonrole reset` | `manage_roles` |

**Aliases:** `br`

**Styles:** `primary` (blurple), `secondary` (grey), `success` (green), `danger` (red)

**Example:**
```
,buttonrole add https://discord.com/channels/123/456/789 primary 🎮 Gamer @Gamer
,buttonrole add https://discord.com/channels/123/456/789 success 🎵 Music @Music
```

{% hint style="info" %}
- Up to **25 buttons** per message
- Buttons can only be added to messages sent by the bot
{% endhint %}

---

## Button Responses

Add interactive buttons to messages that send a response when clicked.

| Command | Description | Syntax | Permission |
|---------|-------------|--------|------------|
| `buttonresponse add` | Add a button response | `buttonresponse add (message link) (style) (emote) (name), (response)` | `manage_guild` |
| `buttonresponse remove` | Remove a button response | `buttonresponse remove (message link) (button id)` | `manage_guild` |
| `buttonresponse removeall` | Remove all button responses from a message | `buttonresponse removeall (message link)` | `manage_guild` |
| `buttonresponse list` | List all button responses | `buttonresponse list` | `manage_guild` |
| `buttonresponse reset` | Remove all button responses | `buttonresponse reset` | `manage_guild` |

**Aliases:** `bresp`

**Example:**
```
,buttonresponse add https://discord.com/channels/123/456/789 primary 📜 Rules, Here are the server rules...
,buttonresponse add https://discord.com/channels/123/456/789 success ❓ FAQ, Check out our FAQ at...
```

{% hint style="info" %}
- Up to **25 buttons** per message
- Use the button ID from `,buttonresponse list` to remove specific buttons
{% endhint %}

---

## Filter (AutoMod)

Manage server content filtering using Discord's native AutoMod system.

### Word Filter

| Command | Description | Syntax | Permission |
|---------|-------------|--------|------------|
| `filter add` | Add a word to the filter | `filter add (word)` | `manage_guild` |
| `filter remove` | Remove a word from the filter | `filter remove (word)` | `manage_guild` |
| `filter exempt` | Exempt a role, user, or channel | `filter exempt (role/user/channel)` | `manage_guild` |
| `filter list` | List all filtered words | `filter list` | `manage_guild` |

**Example:**
```
,filter add badword
,filter remove badword
,filter exempt @Moderators
,filter exempt #bot-commands
```

### Link Filter

| Command | Description | Syntax | Permission |
|---------|-------------|--------|------------|
| `filter links on` | Enable link filtering | `filter links on` | `manage_guild` |
| `filter links off` | Disable link filtering | `filter links off` | `manage_guild` |
| `filter links exempt` | Exempt a role or channel | `filter links exempt (role/channel)` | `manage_guild` |

**Example:**
```
,filter links on
,filter links exempt @Trusted
,filter links off
```

### Invite Filter

| Command | Description | Syntax | Permission |
|---------|-------------|--------|------------|
| `filter invites on` | Enable invite link filtering | `filter invites on` | `manage_guild` |
| `filter invites off` | Disable invite link filtering | `filter invites off` | `manage_guild` |
| `filter invites exempt` | Exempt a role or channel | `filter invites exempt (role/channel)` | `manage_guild` |

**Example:**
```
,filter invites on
,filter invites exempt #partnerships
,filter invites off
```

### Reset Filters

| Command | Description | Syntax | Permission |
|---------|-------------|--------|------------|
| `filter reset` | Reset all filters (removes all AutoMod rules) | `filter reset` | `manage_guild` |

{% hint style="info" %}
- Up to **1000 filtered words**
- Up to **20 exempt roles** and **50 exempt channels** per filter
- Uses Discord's native AutoMod for reliable filtering
{% endhint %}

{% hint style="warning" %}
The bot requires `Manage Server` permission to create and manage AutoMod rules.
{% endhint %}
