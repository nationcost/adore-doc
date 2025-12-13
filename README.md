---
description: >-
  Learn how to set up Adore in your server or enhance your everyday use with
  commands & more.
icon: book-open-reader
---

# Introduction

Welcome to the official Adore documentation! Adore is a powerful, feature-rich Discord bot designed to help you manage and enhance your server.

## Features

- **Moderation** - Ban, kick, mute, jail, warn, and more
- **Welcome & Leave Messages** - Customizable greet messages with embeds
- **Autoresponder** - Automatic responses to trigger words
- **Autoreact** - Automatic reactions to messages
- **Role Management** - Autoroles, mass role operations, and more
- **Customization** - Custom bot avatar, banner, bio, and embed colors
- **Utility** - Aliases, reminders, color lookup, and more

---

## Quick Start

### 1. Invite the Bot

[Click here to invite Adore](https://discord.com/oauth2/authorize) to your server.

### 2. Set Up Moderation

Run these commands to set up moderation features:

```
,setup
,setupmute
```

### 3. Configure Your Server

- Set a custom prefix: `,prefix set !`
- Add welcome messages: `,welcome add #channel Welcome {user.mention}!`
- Set up autoroles: `,autorole add @Member`

---

## Default Prefix

{% hint style="info" %}
The default prefix is `,` (comma). Use `,prefix set (symbol)` to change it for your server.
{% endhint %}

---

## Command Syntax

Throughout this documentation, you'll see command syntax like this:

- `(required)` - This argument is required
- `[optional]` - This argument is optional
- `...` - Multiple values can be provided

**Example:**
```
,ban (user) [reason]
```
- `user` is required
- `reason` is optional

---

## Getting Help

### In Discord

Use the help command to get information about any command:

```
,help
,help ban
,help welcome
```

### Support Server

Join our [support server](https://adore.rest/server) for help, updates, and more.

---

## Links

- [Invite Bot](https://discord.com/oauth2/authorize)
- [Support Server](https://adore.rest/server)
- [Commands](https://adore.rest/commands)
