---
description: Customize the bot's appearance in your server.
icon: palette
---

# Customization Commands

Customize how the bot looks and behaves in your server.

{% hint style="info" %}
All customization commands have a **60 second cooldown** per server.
{% endhint %}

## Bot Avatar

| Command | Description | Syntax | Permission |
|---------|-------------|--------|------------|
| `customize avatar` | Set a custom avatar for the bot in your server | `customize avatar [url]` | `manage_guild` |

**Examples:**
```
,customize avatar https://example.com/avatar.png
,customize avatar (with image attachment)
,customize avatar (leave empty to reset)
```

---

## Bot Banner

| Command | Description | Syntax | Permission |
|---------|-------------|--------|------------|
| `customize banner` | Set a custom banner for the bot in your server | `customize banner [url]` | `manage_guild` |

**Examples:**
```
,customize banner https://example.com/banner.png
,customize banner (with image attachment)
,customize banner (leave empty to reset)
```

---

## Bot Bio

| Command | Description | Syntax | Permission |
|---------|-------------|--------|------------|
| `customize bio` | Set a custom bio for the bot in your server | `customize bio [text]` | `manage_guild` |

**Examples:**
```
,customize bio Welcome to our server!
,customize bio (leave empty to reset)
```

{% hint style="warning" %}
Bio must be **190 characters or less**.
{% endhint %}

---

## Embed Color

| Command | Description | Syntax | Permission |
|---------|-------------|--------|------------|
| `customize color` | Set the default embed color for your server | `customize color [hex/name]` | `owner` |

**Examples:**
```
,customize color #ff5733
,customize color red
,customize color 255, 87, 51
,customize color (leave empty to reset)
```

{% hint style="warning" %}
Only the **server owner** can change the embed color.
{% endhint %}

---

## Supported Image Formats

- PNG
- JPG / JPEG
- GIF
- WEBP
