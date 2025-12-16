---
description: Complete guide to creating custom embeds with all properties and options.
icon: window-maximize
---

# Embed Builder Reference

Create rich embeds with titles, descriptions, images, fields, buttons, and more.

---

## Supported Commands

The following commands support custom embeds:

| Command | Description |
|---------|-------------|
| `welcome` | Welcome message when members join |
| `leave` | Leave message when members leave |
| `boost` | Boost message when members boost |
| `autoresponder` | Custom trigger responses |
| `stickymessage` | Persistent channel messages |
| `embeds` | Test/preview embed code |

---

## Basic Structure

Embeds use the `{embed}` tag followed by properties separated by `$v`:

```
{embed}$v{property: value}$v{property: value}
```

**Example:**
```
,ce {embed}$v{title: Hello World}$v{description: This is my first embed!}$v{color: #5865F2}
```

---

## Embed Properties

### Title

The main title of the embed.

```
{title: Your Title Here}
```

**Character Limit:** 256 characters

---

### Description

The main body text of the embed. Supports markdown.

```
{description: Your description here with **bold** and *italic* text}
```

**Character Limit:** 4096 characters

**Line Breaks:** Use `\n` for new lines:
```
{description: Line 1\nLine 2\nLine 3}
```

---

### Color

The colored bar on the left side of the embed.

```
{color: #5865F2}
{color: #ff0000}
```

**Formats:**
- Hex with `#`: `#5865F2`
- Hex without `#`: `5865F2`

---

### Author

Appears at the top of the embed with optional icon and link.

**Basic:**
```
{author: Author Name}
```

**With Icon:**
```
{author: Author Name && https://example.com/icon.png}
```

**With Icon and URL:**
```
{author: Author Name && https://example.com/icon.png && https://example.com}
```

**Character Limit:** 256 characters for name

---

### Thumbnail

Small image in the top-right corner.

```
{thumbnail: https://example.com/image.png}
{thumbnail: {user.avatar}}
```

---

### Image

Large image at the bottom of the embed.

```
{image: https://example.com/image.png}
{image: {guild.icon}}
```

---

### Footer

Text at the bottom of the embed with optional icon.

**Basic:**
```
{footer: Footer text here}
```

**With Icon:**
```
{footer: Footer text && https://example.com/icon.png}
```

**Character Limit:** 2048 characters

---

### Timestamp

Adds the current timestamp to the footer.

```
{timestamp}
```

Shows as: `Today at 3:45 PM`

---

### Fields

Add multiple fields to organize information.

```
{field: Field Name && Field Value && inline}
```

**Parameters:**
1. **Name** - Field title (required)
2. **Value** - Field content (required)
3. **Inline** - `true` or `false` (optional, default: false)

**Examples:**
```
{field: Members && 1500 && true}
{field: Created && January 2024 && true}
{field: Description && This is a longer description that takes the full width && false}
```

**Inline Fields:** Set to `true` to display fields side by side (up to 3 per row).

**Character Limits:**
- Name: 256 characters
- Value: 1024 characters
- Max fields: 25

---

### Content (Message Text)

Add text outside the embed.

```
{content: This text appears above the embed}
{message: This also works}
```

---

## Buttons

Add interactive buttons below the embed.

### Link Buttons

```
{button: https://example.com && Button Label}
{button: https://example.com && Click Me && 🔗}
```

**Parameters:**
1. **URL** - The link (must start with `http://` or `https://`)
2. **Label** - Button text
3. **Emoji** - Optional emoji

### Styled Buttons

```
{button: primary && Button Label}
{button: success && Click Me && ✅}
```

**Styles:**
| Style | Color | Aliases |
|-------|-------|---------|
| `primary` | Blurple | `blue` |
| `secondary` | Gray | `gray`, `grey` |
| `success` | Green | `green` |
| `danger` | Red | `red` |

**Parameters:**
1. **Style** - Button style
2. **Label** - Button text
3. **Emoji** - Optional emoji

{% hint style="info" %}
Non-link buttons are decorative only and don't perform actions.
{% endhint %}

---

## Complete Examples

### Simple Announcement

```
,ce {embed}$v{title: 📢 Announcement}$v{description: Server maintenance will occur tonight at 10 PM EST.}$v{color: #ff9900}
```

### Welcome Embed

```
,ce {embed}$v{author: Welcome! && {user.avatar}}$v{title: {user.name} joined the server}$v{description: You are member **#{guild.count}**!\n\nMake sure to read the rules in #rules}$v{color: #00ff00}$v{thumbnail: {user.avatar}}$v{footer: Enjoy your stay!}$v{timestamp}
```

### Server Info

```
,ce {embed}$v{author: {guild.name} && {guild.icon}}$v{title: Server Information}$v{field: Members && {guild.count} && true}$v{field: Boosts && {guild.boost_count} && true}$v{field: Created && <t:{guild.created_at_timestamp}:R> && true}$v{color: #5865F2}$v{thumbnail: {guild.icon}}
```

### With Buttons

```
,ce {embed}$v{title: Useful Links}$v{description: Check out these resources!}$v{color: #5865F2}$v{button: https://adore.rest/server && Join Server && 🎮}$v{button: https://adore.rest/commands && Commands && 📚}
```

### Full Featured

```
,ce {content: @everyone New update!}$v{embed}$v{author: Adore Bot && {guild.icon} && https://adore.bot}$v{title: Version 2.0 Released!}$v{description: We've added tons of new features:\n\n• New moderation commands\n• Improved embed builder\n• Bug fixes}$v{field: Downloads && 10,000+ && true}$v{field: Rating && ⭐⭐⭐⭐⭐ && true}$v{color: #5865F2}$v{image: https://example.com/banner.png}$v{footer: Thanks for using Adore! && {guild.icon}}$v{timestamp}$v{button: https://adore.rest/server && Support Server}
```

---

## Character Limits Summary

| Element | Limit |
|---------|-------|
| Title | 256 |
| Description | 4096 |
| Author Name | 256 |
| Field Name | 256 |
| Field Value | 1024 |
| Footer Text | 2048 |
| Total Embed | 6000 |
| Max Fields | 25 |

---

## Tips & Tricks

{% hint style="success" %}
**Testing:** Always test your embed with `,ce` before using it in welcome messages or autoresponders.
{% endhint %}

{% hint style="info" %}
**Copy Existing:** Use `,copyembed` to get the code from any embed message.
{% endhint %}

{% hint style="warning" %}
**Empty Embeds:** An embed must have at least one visible element (title, description, field, image, etc.) or it will fail.
{% endhint %}

{% hint style="info" %}
**Markdown:** Descriptions and field values support Discord markdown: `**bold**`, `*italic*`, `__underline__`, `~~strikethrough~~`, `` `code` ``, and `> quotes`.
{% endhint %}
