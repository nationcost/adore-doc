---
description: Common issues and how to fix them when creating embeds and containers.
icon: circle-question
---

# Troubleshooting

Common problems and solutions when working with embeds, containers, and variables.

---

## Embed Issues

### "Embed is empty" Error

**Problem:** The bot says the embed is empty.

**Solution:** An embed must have at least one visible element. Add a title, description, field, or image.

```
❌ {embed}$v{color: #5865F2}
✅ {embed}$v{title: Hello}$v{color: #5865F2}
```

---

### Embed Not Showing Color

**Problem:** The colored bar isn't appearing.

**Solution:** Make sure you're using the correct hex format with `#`:

```
❌ {color: 5865F2}
❌ {color: blue}
✅ {color: #5865F2}
```

---

### Image Not Loading

**Problem:** Thumbnail or image isn't showing.

**Solution:** 
1. Make sure the URL is a direct image link (ends in `.png`, `.jpg`, `.gif`, etc.)
2. The image must be publicly accessible (not behind a login)
3. Discord CDN links work best

```
❌ {image: https://example.com/gallery}
✅ {image: https://example.com/image.png}
✅ {image: {user.avatar}}
```

---

### Fields Not Inline

**Problem:** Fields are stacking vertically instead of side by side.

**Solution:** Set the third parameter to `true`:

```
❌ {field: Name && Value}
✅ {field: Name && Value && true}
```

Note: You need 2-3 inline fields for them to appear side by side.

---

### Line Breaks Not Working

**Problem:** Text appears on one line instead of multiple.

**Solution:** Use `\n` for line breaks:

```
❌ {description: Line 1
Line 2}
✅ {description: Line 1\nLine 2}
```

---

### Author Icon Not Showing

**Problem:** Author section shows name but no icon.

**Solution:** Use `&&` to separate name and icon URL:

```
❌ {author: Name {user.avatar}}
✅ {author: Name && {user.avatar}}
```

---

## Container Issues

### Container Not Displaying

**Problem:** Container shows as plain text or doesn't render.

**Possible causes:**
1. User is on an older Discord client
2. Syntax error in the container code
3. Missing `{container}` tag

**Solution:** Test with a simple container first:
```
,ce {container}$v{text: Hello}$v{color: #5865F2}
```

---

### Section Thumbnail Not Showing

**Problem:** Section text appears but no thumbnail.

**Solution:** Make sure you're using `&&` to separate text and URL:

```
❌ {section: Text {user.avatar}}
✅ {section: Text && {user.avatar}}
```

---

### Gallery Images Not Loading

**Problem:** Gallery shows empty or broken images.

**Solution:** 
1. Use direct image URLs
2. Separate URLs with `&&`
3. Make sure all URLs are valid

```
✅ {gallery: https://url1.png && https://url2.png && https://url3.png}
```

---

## Variable Issues

### Variable Shows as Plain Text

**Problem:** `{user.name}` appears literally instead of the username.

**Possible causes:**
1. Typo in variable name
2. Variable doesn't exist
3. Using in wrong context

**Solution:** Check the variable name against the [Variables Reference](variables.md).

```
❌ {username}
❌ {user.username}
✅ {user.name}
```

---

### Variable Shows "N/A"

**Problem:** Variable returns "N/A" instead of a value.

**Explanation:** Some variables return "N/A" when the data doesn't exist:
- `{user.guild_avatar}` → N/A if user has no server avatar
- `{guild.banner}` → N/A if server has no banner
- `{guild.vanity}` → N/A if server has no vanity URL

**Solution:** This is expected behavior. Consider using conditional text or a different variable.

---

### Timestamp Shows Wrong Time

**Problem:** Timestamp shows incorrect date/time.

**Solution:** Use Discord's dynamic timestamps with the `_timestamp` variables:

```
❌ {user.joined_at}
✅ <t:{user.joined_at_timestamp}:R>
```

Discord timestamps automatically adjust to the viewer's timezone.

---

### User Variables Empty in Welcome Messages

**Problem:** User variables don't work in welcome messages.

**Solution:** This shouldn't happen. Make sure you're using the correct variable format:

```
✅ {user.mention}
✅ {user.name}
✅ {user.avatar}
```

If still not working, try recreating the welcome message.

---

## Button Issues

### Button Not Clickable

**Problem:** Button appears but doesn't do anything when clicked.

**Explanation:** Only link buttons (with URLs) are functional. Styled buttons are decorative.

**Solution:** Use a URL for clickable buttons:

```
❌ {button: primary && Click Me}        → Decorative only
✅ {button: https://example.com && Click Me}  → Clickable link
```

---

### Button URL Not Working

**Problem:** Link button doesn't open the URL.

**Solution:** Make sure the URL starts with `http://` or `https://`:

```
❌ {button: example.com && Click}
❌ {button: discord.gg/server && Click}
✅ {button: https://example.com && Click}
✅ {button: https://discord.gg/server && Click}
```

---

## Autoresponder Issues

### Autoresponder Not Triggering

**Problem:** Bot doesn't respond to the trigger.

**Possible causes:**
1. Trigger is case-sensitive (it's not, but check spelling)
2. Strict mode requires exact match
3. Bot doesn't have permission to send messages

**Solutions:**
- For partial matches, use `--not_strict`:
  ```
  ,ar add hello, Hi there! --not_strict
  ```
- Check bot permissions in the channel
- Verify the trigger exists with `,ar list`

---

### Autoresponder Responding Too Much

**Problem:** Bot responds when it shouldn't.

**Solution:** Remove `--not_strict` flag for exact matching only:

```
,ar remove hello
,ar add hello, Hi there!
```

Now it only triggers on exactly "hello", not "hello there".

---

### Mentions Not Working in Autoresponder

**Problem:** `{user.mention}` doesn't ping the user.

**Solution:** Add `--mention` flag to enable pings:

```
,ar add hello, Hi {user.mention}! --mention
```

---

## General Tips

### Testing Your Code

Always test with `,ce` before using in welcome/autoresponder:

```
,ce {embed}$v{title: Test}$v{description: Testing my embed}
```

### Copying Existing Embeds

Use `,copyembed` to get the code from any message:

```
,copyembed 123456789012345678
,copyembed (reply to a message)
```

### Character Limits

If your embed fails silently, you might be hitting character limits:

| Element | Limit |
|---------|-------|
| Title | 256 |
| Description | 4096 |
| Field Name | 256 |
| Field Value | 1024 |
| Footer | 2048 |
| Author Name | 256 |
| Total Embed | 6000 |

### Escaping Special Characters

If you need literal `{` or `}` in your text, there's currently no escape method. Use alternative characters or wording.

---

## Still Having Issues?

1. Double-check your syntax against the reference pages
2. Test with a minimal example first
3. Join our [support server](https://adore.rest/server) for help
