---
description: Complete guide to creating containers using Discord's Components V2.
icon: box
---

# Container Builder Reference

Containers are Discord's new Components V2 system, offering more flexible layouts than traditional embeds.

{% hint style="info" %}
Containers are a newer Discord feature and may not display correctly on older Discord clients.
{% endhint %}

---

## Basic Structure

Containers use the `{container}` tag followed by components separated by `$v`:

```
{container}$v{component: value}$v{component: value}
```

**Example:**
```
,ce {container}$v{text: # Hello World}$v{text: Welcome to my server!}$v{color: #5865F2}
```

---

## Container Components

### Text

Add text content with full markdown support.

```
{text: Your text here}
{text: # Heading}
{text: **Bold** and *italic* text}
{text: Line 1\nLine 2}
```

**Markdown Support:**
- `# Heading 1`
- `## Heading 2`
- `### Heading 3`
- `**bold**`
- `*italic*`
- `__underline__`
- `~~strikethrough~~`
- `` `code` ``
- `> quote`
- Lists with `-` or `*`

---

### Color

Set the accent color (colored bar on the left).

```
{color: #5865F2}
{color: #ff0000}
```

---

### Separator

Add a horizontal line between components.

**Small spacing:**
```
{separator}
{separator:small}
```

**Large spacing:**
```
{separator:large}
```

---

### Section with Thumbnail

Create a section with text and a thumbnail image on the right.

```
{section: Your text here && https://example.com/image.png}
```

**Parameters:**
1. **Text** - The section content (supports markdown)
2. **Thumbnail URL** - Image displayed on the right

**Example:**
```
{section: ## User Profile\n**Name:** John\n**Level:** 50 && {user.avatar}}
```

---

### Image

Add a single image.

```
{image: https://example.com/image.png}
{image: {user.avatar}}
{image: {guild.icon}}
```

---

### Gallery

Add multiple images in a gallery layout.

```
{gallery: https://url1.png && https://url2.png && https://url3.png}
```

Images are displayed in a grid format.

---

### Content (Message Text)

Add text that appears above the container.

```
{content: This text appears above the container}
{message: This also works}
```

---

### Buttons

Add interactive buttons at the bottom.

**Link Buttons:**
```
{button: https://example.com && Button Label}
{button: https://example.com && Click Me && 🔗}
```

**Styled Buttons:**
```
{button: primary && Button Label}
{button: success && Click Me && ✅}
```

**Styles:**
| Style | Color |
|-------|-------|
| `primary` | Blurple |
| `secondary` | Gray |
| `success` | Green |
| `danger` | Red |

---

## Complete Examples

### Simple Container

```
,ce {container}$v{text: # Welcome!}$v{text: Thanks for joining our server.}$v{color: #5865F2}
```

### User Profile

```
,ce {container}$v{section: # {user.name}\n-# @{user.name}\n\n**Joined:** <t:{user.joined_at_timestamp}:R> && {user.avatar}}$v{separator}$v{text: **Roles:** {user.role_list}}$v{color: #5865F2}
```

### Server Info

```
,ce {container}$v{text: # {guild.name}}$v{image: {guild.icon}}$v{separator}$v{text: **Members:** {guild.count}\n**Boosts:** {guild.boost_count}\n**Created:** <t:{guild.created_at_timestamp}:D>}$v{color: #5865F2}
```

### With Gallery

```
,ce {container}$v{text: # Photo Gallery}$v{gallery: https://url1.png && https://url2.png && https://url3.png}$v{separator}$v{text: -# Click images to expand}$v{color: #5865F2}
```

### With Buttons

```
,ce {container}$v{text: # Quick Links}$v{text: Check out these useful resources!}$v{separator}$v{button: https://discord.gg/adore && Join Server && 🎮}$v{button: https://docs.adore.bot && Docs && 📚}$v{color: #5865F2}
```

### Full Featured

```
,ce {container}$v{section: # Welcome {user.name}!\n\nYou are member **#{guild.count}** && {user.avatar}}$v{separator}$v{text: ## Getting Started\n- Read the rules in #rules\n- Get roles in #roles\n- Introduce yourself in #introductions}$v{separator:large}$v{text: -# Need help? Open a ticket!}$v{button: https://discord.gg/adore && Support && 🎫}$v{color: #00ff00}
```

---

## Containers vs Embeds

| Feature | Embed | Container |
|---------|-------|-----------|
| Colored bar | Yes | Yes |
| Title | Yes | Yes (use `# Title`) |
| Description | Yes | Yes (use `{text}`) |
| Fields | Yes | Yes (use multiple `{text}`) |
| Thumbnail | Yes | Yes (use `{section}`) |
| Image | Yes | Yes |
| Gallery | No | Yes |
| Footer | Yes | Yes (use `-# text`) |
| Author | Yes | Yes (use `{text}`) |
| Timestamp | Yes | Yes (use variables) |
| Buttons | Yes | Yes |
| Separators | No | Yes |
| Sections | No | Yes |
| Headings | No | Yes (markdown) |

---

## When to Use Containers

**Use Containers when you need:**
- Multiple images (gallery)
- Visual separators
- Section layouts with thumbnails
- Markdown headings
- More flexible text layouts

**Use Embeds when you need:**
- Traditional Discord embed look
- Fields with inline support
- Author with icon and link
- Footer with icon
- Automatic timestamp

---

## Tips

{% hint style="success" %}
**Subtext:** Use `-#` for small/muted text: `{text: -# This is small text}`
{% endhint %}

{% hint style="info" %}
**Headings:** Use markdown headings for structure: `# H1`, `## H2`, `### H3`
{% endhint %}

{% hint style="warning" %}
**Compatibility:** Containers may not display correctly on older Discord clients or some third-party apps.
{% endhint %}

{% hint style="info" %}
**Copy Existing:** Use `,copyembed` on a message with a container to get its code.
{% endhint %}
