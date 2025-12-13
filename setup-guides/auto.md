---
description: Set up automatic reactions and responses.
icon: robot
---

# Autoresponder & Autoreact

## Autoresponder

Automatically respond to messages containing specific trigger words.

### Adding an Autoresponse

The syntax uses a comma to separate the trigger and response:

```
,autoresponder add trigger, response
```

**Example:**
```
,ar add hello, Hello there! 👋
,ar add ping, Pong! 🏓
```

### Response Flags

Add flags to customize behavior:

| Flag | Description |
|------|-------------|
| `--reply` | Reply to the triggering message |
| `--not_strict` | Match trigger anywhere in message |
| `--delete N` | Delete response after N seconds (1-10) |

**Examples:**
```
,ar add hello, Hello! --reply
,ar add lol, 😂 --not_strict
,ar add secret, This will disappear... --delete 5
,ar add hi, Hey {user.mention}! --reply --not_strict
```

### Strict vs Not Strict

**Strict (default):** Message must exactly match the trigger
- Trigger: `hello`
- ✅ "hello" → responds
- ❌ "hello there" → no response
- ❌ "say hello" → no response

**Not Strict (`--not_strict`):** Trigger can appear anywhere
- Trigger: `hello`
- ✅ "hello" → responds
- ✅ "hello there" → responds
- ✅ "say hello" → responds

### Using Variables

You can use variables in your responses:

```
,ar add hello, Hello {user.mention}! Welcome to {guild.name}!
```

See [Variables](#variables) for the full list.

### Using Embeds

Create embed responses:

```
,ar add info, {embed}$v{title: Server Info}$v{description: Welcome to {guild.name}!}$v{color: #5865F2}
```

### Managing Autoresponders

```
,ar list              # List all autoresponders
,ar view hello        # Preview the response for "hello"
,ar remove hello      # Remove the "hello" trigger
,ar reset             # Remove all autoresponders
```

{% hint style="info" %}
You can have up to **100 autoresponders** per server.
{% endhint %}

---

## Autoreact

Automatically react to messages containing specific trigger words.

### Adding Autoreacts

```
,autoreact add 👍 hello
,autoreact add ❤️ love
,autoreact add <:custom:123456789> nice
```

### Multiple Reactions

Add multiple emojis to the same trigger:

```
,autoreact add 👍 hello
,autoreact add 👋 hello
,autoreact add ❤️ hello
```

Now messages containing "hello" will get 👍, 👋, and ❤️ reactions.

### Managing Autoreacts

```
,autoreact list                    # List all autoreacts
,autoreact remove 👍 hello         # Remove 👍 from "hello"
,autoreact deleteall hello         # Remove all reactions for "hello"
,autoreact reset                   # Remove all autoreacts
```

{% hint style="info" %}
- Up to **5 reactions** per trigger
- Up to **100 triggers** per server
{% endhint %}

---

## Channel Reactions

React to ALL messages in specific channels (great for media/art channels).

### Adding Channel Reactions

```
,reaction add #media 👍 👎
,reaction add #art ❤️ 🔥 ⭐
```

### Managing Channel Reactions

```
,reaction list              # List all channel reactions
,reaction remove #media     # Remove reactions from #media
,reaction reset             # Remove all channel reactions
```

{% hint style="info" %}
- Up to **3 reactions** per channel
- Slowmode is automatically set to 3 seconds
{% endhint %}

---

## Variables

Use these in autoresponder messages:

### User Variables
| Variable | Description |
|----------|-------------|
| `{user}` | Username |
| `{user.name}` | Username |
| `{user.mention}` | User mention |
| `{user.id}` | User ID |
| `{user.avatar}` | Avatar URL |

### Server Variables
| Variable | Description |
|----------|-------------|
| `{guild}` | Server name |
| `{guild.name}` | Server name |
| `{guild.id}` | Server ID |
| `{guild.count}` | Member count |
| `{guild.icon}` | Server icon URL |

---

## Examples

### FAQ Bot
```
,ar add how do i get roles, Check out #roles to pick your roles! --reply
,ar add where are the rules, Read the rules in #rules --reply --delete 10
```

### Fun Responses
```
,ar add good morning, Good morning {user.name}! ☀️ --not_strict
,ar add good night, Sweet dreams! 🌙 --not_strict --reply
```

### Media Channel Setup
```
,reaction add #selfies ❤️ 🔥
,reaction add #art ⭐ 👏 ❤️
,reaction add #memes 😂 👍
```
