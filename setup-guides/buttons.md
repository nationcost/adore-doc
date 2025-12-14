---
description: Complete guide to setting up button roles and button responses.
icon: square
---

# Button Setup Guide

Buttons allow you to create interactive messages where users can click to receive roles or get information.

---

## Overview

Adore supports two types of buttons:

| Type | Purpose | Permission |
|------|---------|------------|
| **Button Roles** | Give/remove roles when clicked | `manage_roles` |
| **Button Responses** | Send a message when clicked | `manage_guild` |

---

## Button Styles

Both button types support these styles:

| Style | Color | Aliases |
|-------|-------|---------|
| `primary` | Blurple | `blurple` |
| `secondary` | Grey | `grey`, `gray` |
| `success` | Green | `green` |
| `danger` | Red | `red` |

---

## Button Roles

Button roles let users self-assign roles by clicking a button.

### Commands

| Command | Description | Syntax |
|---------|-------------|--------|
| `buttonrole add` | Add a button role | `buttonrole add (message link) (style) (emote) (name) (role)` |
| `buttonrole remove` | Remove a button role | `buttonrole remove (message link) (role)` |
| `buttonrole removeall` | Remove all buttons from a message | `buttonrole removeall (message link)` |
| `buttonrole list` | List all button roles | `buttonrole list` |
| `buttonrole reset` | Remove all button roles | `buttonrole reset` |

### Setup Steps

**Step 1:** Create a message using the bot

```
,ce {embed}$v{title: 🎮 Role Selection}$v{description: Click a button below to get your role!}$v{color: #5865F2}
```

**Step 2:** Copy the message link (Right-click → Copy Message Link)

**Step 3:** Add button roles to the message

```
,buttonrole add https://discord.com/channels/123/456/789 primary 🎮 Gamer @Gamer
,buttonrole add https://discord.com/channels/123/456/789 success 🎵 Music @Music
,buttonrole add https://discord.com/channels/123/456/789 danger 🎬 Movies @Movies
```

### How It Works

- When a user clicks a button, they receive the associated role
- If they already have the role, clicking removes it (toggle behavior)
- Users can have multiple roles from the same message

### Example Setup

```
,ce {embed}$v{title: Choose Your Roles}$v{description: Select the roles you want:

🎮 **Gamer** - Get pinged for gaming events
🎵 **Music** - Get pinged for music drops
📢 **Announcements** - Get server announcements}$v{color: #5865F2}
```

Then add the buttons:
```
,buttonrole add [message link] primary 🎮 Gamer @Gamer
,buttonrole add [message link] success 🎵 Music @Music  
,buttonrole add [message link] secondary 📢 Announcements @Announcements
```

---

## Button Responder

Button responder sends a message (visible only to the clicker) when clicked.

### Commands

| Command | Description | Syntax |
|---------|-------------|--------|
| `buttonresponder add` | Add a button response | `buttonresponder add (message link) (style) (emote) (name), (response)` |
| `buttonresponder remove` | Remove a button response | `buttonresponder remove (message link) (button id)` |
| `buttonresponder removeall` | Remove all buttons from a message | `buttonresponder removeall (message link)` |
| `buttonresponder list` | List all button responses | `buttonresponder list` |
| `buttonresponder reset` | Remove all button responses | `buttonresponder reset` |

### Setup Steps

**Step 1:** Create a message using the bot

```
,ce {embed}$v{title: ℹ️ Server Information}$v{description: Click a button to learn more!}$v{color: #5865F2}
```

**Step 2:** Copy the message link

**Step 3:** Add button responses

```
,buttonresponder add https://discord.com/channels/123/456/789 primary 📜 Rules, **Server Rules:**
1. Be respectful
2. No spam
3. Follow Discord TOS
```

### Using Embeds in Responses

You can use embed syntax in your responses:

```
,buttonresponder add [link] success ❓ FAQ, {embed}$v{title: FAQ}$v{description: **Q: How do I get roles?**
A: Use the role selection menu!}$v{color: #00ff00}
```

### Example Setup

```
,ce {embed}$v{title: 📚 Information Hub}$v{description: Click a button to get information:}$v{color: #5865F2}
```

Then add responses:
```
,buttonresponder add [link] primary 📜 Rules, **Our Rules:**\n1. Be kind\n2. No spam\n3. Have fun!
,buttonresponder add [link] success ❓ FAQ, **FAQ:**\nQ: How to get roles?\nA: Check #roles!
,buttonresponder add [link] danger 🎫 Support, Need help? Create a ticket in #support!
```

---

## Limits

| Feature | Limit |
|---------|-------|
| Buttons per message | 25 |
| Button label length | 80 characters |
| Response length | 2000 characters |

---

## Important Notes

{% hint style="warning" %}
**Buttons can only be added to messages sent by the bot.** Use `,ce` (createembed) to create the initial message.
{% endhint %}

{% hint style="info" %}
**Button responses are ephemeral** - only the user who clicked can see them.
{% endhint %}

{% hint style="info" %}
**To remove a button response**, use the button ID shown in `,buttonresponder list`.
{% endhint %}

---

## Troubleshooting

### "Could not find that message"
- Make sure the message link is from this server
- Ensure the message still exists
- Check that the link format is correct

### "I can only add buttons to my own messages"
- Create a new message using `,ce` first
- You cannot add buttons to messages sent by other users or bots

### Buttons not appearing
- Check if you have the required permissions
- Verify the message link is correct
- Try using `,buttonrole list` or `,buttonresponder list` to see if it was added

### Role not being given
- Ensure the bot's role is higher than the role being assigned
- Check that the bot has `Manage Roles` permission
- Verify the role still exists

---

## Variables in Responses

Button responses support all standard variables:

| Variable | Description |
|----------|-------------|
| `{user.mention}` | Mentions the user who clicked |
| `{user.name}` | User's display name |
| `{user.avatar}` | User's avatar URL |
| `{guild.name}` | Server name |
| `{guild.icon}` | Server icon URL |
| `{guild.members}` | Member count |

**Example:**
```
,buttonresponder add [link] primary 👋 Welcome, Welcome {user.mention}! You're member #{guild.members}!
```

See the [Variables Reference](../reference/variables.md) for the full list.

---

## Using Buttons with Autoresponder

You can trigger buttons through the autoresponder using `{button:ID}`.

### Setup

**Step 1:** Create a button response first
```
,buttonresponder add [message link] primary 🛒 Shop, Welcome to the shop! Here are our items...
```

**Step 2:** Note the button's position in the list
```
,buttonresponder list
```
The number shown (e.g., `01`) is the button ID.

**Step 3:** Create an autoresponder that sends the button
```
,ar add shop, {button:1}
```

### Behavior

When someone types the trigger word:
- Their message is **deleted** (keeps the channel clean)
- The button appears in the channel
- Clicking the button shows the response (ephemeral)

### Keep the Trigger Message

If you don't want the trigger message deleted, use `--keep`:
```
,ar add shop, {button:1} --keep
```

### Example Use Cases

**Quick access buttons:**
```
,ar add rules, {button:1}
,ar add faq, {button:2}
,ar add help, {button:3}
```

**With --keep for context:**
```
,ar add !shop, {button:1} --keep
```

{% hint style="info" %}
The button ID corresponds to the order in `,buttonresponder list`. If you remove a button, the IDs may shift.
{% endhint %}
