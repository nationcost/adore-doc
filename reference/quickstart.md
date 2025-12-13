---
description: Quick reference cheatsheet for embeds, containers, and variables.
icon: bolt
---

# Quick Reference Cheatsheet

A quick reference for the most commonly used syntax.

---

## Most Used Variables

```
{user}              → Username
{user.mention}      → @Username (clickable)
{user.avatar}       → Avatar URL
{user.id}           → User ID

{guild}             → Server name
{guild.name}        → Server name
{guild.count}       → Member count
{guild.icon}        → Server icon URL

{channel.mention}   → #channel (clickable)
```

---

## Basic Embed Template

```
{embed}$v{title: Your Title}$v{description: Your description}$v{color: #5865F2}
```

**With all common elements:**
```
{embed}$v{author: Author && {user.avatar}}$v{title: Title}$v{description: Description}$v{color: #5865F2}$v{thumbnail: {user.avatar}}$v{image: URL}$v{footer: Footer text}$v{timestamp}
```

---

## Basic Container Template

```
{container}$v{text: # Title}$v{text: Description}$v{color: #5865F2}
```

**With section:**
```
{container}$v{section: # Title\nDescription && {user.avatar}}$v{separator}$v{text: More content}$v{color: #5865F2}
```

---

## Common Patterns

### Welcome Message (Plain Text)
```
Welcome {user.mention} to **{guild.name}**! 🎉
You are member #{guild.count}
```

### Welcome Message (Embed)
```
{embed}$v{title: Welcome!}$v{description: Hey {user.mention}, welcome to **{guild.name}**!\n\nYou are member #{guild.count}}$v{color: #00ff00}$v{thumbnail: {user.avatar}}
```

### Welcome Message (Container)
```
{container}$v{section: # Welcome {user.name}!\nYou are member **#{guild.count}** && {user.avatar}}$v{color: #00ff00}
```

### Leave Message
```
{embed}$v{description: **{user.name}** has left the server.\nWe now have {guild.count} members.}$v{color: #ff0000}
```

### Boost Message
```
{embed}$v{title: 🎉 New Boost!}$v{description: Thank you {user.mention} for boosting!\n\nWe now have **{guild.boost_count}** boosts!}$v{color: #f47fff}$v{thumbnail: {user.avatar}}
```

---

## Fields Quick Reference

```
{field: Name && Value && true}     → Inline field
{field: Name && Value && false}    → Full width field
{field: Name && Value}             → Full width (default)
```

**Multiple inline fields (side by side):**
```
$v{field: Field 1 && Value 1 && true}$v{field: Field 2 && Value 2 && true}$v{field: Field 3 && Value 3 && true}
```

---

## Buttons Quick Reference

**Link button:**
```
{button: https://example.com && Label}
{button: https://example.com && Label && 🔗}
```

**Styled button:**
```
{button: primary && Label}      → Blurple
{button: secondary && Label}    → Gray
{button: success && Label}      → Green
{button: danger && Label}       → Red
```

---

## Discord Timestamps

Use with `_timestamp` variables:

```
<t:{user.joined_at_timestamp}:R>   → "2 months ago"
<t:{user.joined_at_timestamp}:D>   → "January 15, 2024"
<t:{user.joined_at_timestamp}:F>   → "Friday, January 15, 2024 12:30 PM"
```

| Code | Output |
|------|--------|
| `:t` | 12:30 PM |
| `:T` | 12:30:45 PM |
| `:d` | 01/15/2024 |
| `:D` | January 15, 2024 |
| `:f` | January 15, 2024 12:30 PM |
| `:F` | Friday, January 15, 2024 12:30 PM |
| `:R` | 2 months ago |

---

## Autoresponder Flags

```
,ar add trigger, response --reply           → Reply to message
,ar add trigger, response --not_strict      → Match anywhere
,ar add trigger, response --delete 5        → Delete after 5 seconds
,ar add trigger, response --reply --delete 5
```

---

## Color Codes

| Color | Hex |
|-------|-----|
| Discord Blurple | `#5865F2` |
| Green | `#00ff00` |
| Red | `#ff0000` |
| Yellow | `#ffff00` |
| Orange | `#ff9900` |
| Pink | `#ff69b4` |
| Purple | `#9b59b6` |
| Cyan | `#00ffff` |
| White | `#ffffff` |
| Black | `#000000` |

---

## Separator Syntax

```
$v{separator}           → Small spacing
$v{separator:small}     → Small spacing
$v{separator:large}     → Large spacing
```

---

## Line Breaks

Use `\n` for new lines in descriptions and text:

```
{description: Line 1\nLine 2\nLine 3}
{text: Line 1\nLine 2\nLine 3}
```

---

## Markdown in Embeds/Containers

```
**bold**
*italic*
__underline__
~~strikethrough~~
`code`
```code block```
> quote
- list item
```

**Container headings:**
```
# Heading 1
## Heading 2
### Heading 3
-# Small/muted text
```
