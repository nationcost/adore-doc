---
description: Set up welcome, leave, and boost messages for your server.
icon: door-open
---

# Welcome & Leave Messages

## Overview

Adore can send custom messages when:
- A member **joins** the server
- A member **leaves** the server
- A member **boosts** the server

Each message type can be sent to multiple channels (up to 10).

---

## Setting Up Welcome Messages

### Add a Welcome Message

```
,welcome add #welcome Welcome {user.mention} to {guild.name}!
```

### Remove a Welcome Message

```
,welcome remove #welcome
```

### View All Welcome Messages

```
,welcome list
```

### Preview a Welcome Message

```
,welcome view #welcome
```

---

## Setting Up Leave Messages

### Add a Leave Message

```
,leave add #goodbye {user.name} has left the server. We now have {guild.count} members.
```

### Remove a Leave Message

```
,leave remove #goodbye
```

---

## Setting Up Boost Messages

### Add a Boost Message

```
,boost add #boosts Thank you {user.mention} for boosting {guild.name}! 🎉
```

### Remove a Boost Message

```
,boost remove #boosts
```

---

## Variables

Use these variables in your messages:

### User Variables
| Variable | Description | Example |
|----------|-------------|---------|
| `{user}` | Username | `john` |
| `{user.name}` | Username | `john` |
| `{user.mention}` | User mention | `@john` |
| `{user.id}` | User ID | `123456789012345678` |
| `{user.avatar}` | User avatar URL | `https://cdn.discordapp.com/...` |
| `{user.created_at}` | Account creation date | `Jan 1, 2020` |
| `{user.joined_at}` | Server join date | `Jan 1, 2024` |

### Server Variables
| Variable | Description | Example |
|----------|-------------|---------|
| `{guild}` | Server name | `My Server` |
| `{guild.name}` | Server name | `My Server` |
| `{guild.id}` | Server ID | `123456789012345678` |
| `{guild.count}` | Member count | `1000` |
| `{guild.icon}` | Server icon URL | `https://cdn.discordapp.com/...` |

---

## Using Embeds

You can use embed syntax in your messages:

```
,welcome add #welcome {embed}$v{title: Welcome!}$v{description: {user.mention} joined the server}$v{color: #5865F2}$v{thumbnail: {user.avatar}}
```

See the [Embed Builder Guide](embeds.md) for full syntax.

---

## Examples

### Simple Welcome
```
,welcome add #welcome 👋 Welcome {user.mention}!
```

### Detailed Welcome Embed
```
,welcome add #welcome {embed}$v{title: Welcome to {guild.name}!}$v{description: Hey {user.mention}, you are member #{guild.count}!}$v{color: #00ff00}$v{thumbnail: {user.avatar}}$v{footer: Enjoy your stay!}
```

### Leave Message
```
,leave add #goodbye 👋 **{user.name}** has left. We now have {guild.count} members.
```

### Boost Message
```
,boost add #boosts 🎉 **{user.name}** just boosted the server! Thank you so much!
```
