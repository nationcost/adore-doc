---
description: Complete list of all variables you can use in messages, embeds, and containers.
icon: code
---

# Variables Reference

Variables are placeholders that get replaced with actual values when the message is sent. Use them in welcome messages, autoresponders, embeds, and more.

---

## User Variables

Information about the user who triggered the action.

| Variable | Description | Example Output |
|----------|-------------|----------------|
| `{user}` | Full username | `john` or `john#1234` |
| `{user.name}` | Username | `john` |
| `{user.id}` | User ID | `123456789012345678` |
| `{user.mention}` | User mention | `@john` |
| `{user.tag}` | Discriminator | `1234` or `0` |
| `{user.display_name}` | Display/nickname | `Johnny` |
| `{user.avatar}` | Avatar URL | `https://cdn.discordapp.com/...` |
| `{user.display_avatar}` | Display avatar URL | `https://cdn.discordapp.com/...` |
| `{user.guild_avatar}` | Server avatar URL | `https://cdn.discordapp.com/...` or `N/A` |
| `{user.color}` | Role color hex | `#ff5733` |
| `{user.top_role}` | Highest role name | `Admin` |
| `{user.role_list}` | Role mentions (max 20) | `@Admin @Mod @Member` |
| `{user.role_text_list}` | Role names (max 20) | `Admin, Mod, Member` |
| `{user.bot}` | Is bot? | `Yes` or `No` |

### User Dates

| Variable | Description | Example Output |
|----------|-------------|----------------|
| `{user.created_at}` | Account creation date | `2020-01-15 12:30:45 UTC` |
| `{user.created_at_timestamp}` | Creation Unix timestamp | `1579091445` |
| `{user.joined_at}` | Server join date | `2024-01-15 12:30:45 UTC` |
| `{user.joined_at_timestamp}` | Join Unix timestamp | `1705322445` |

### User Boost Info

| Variable | Description | Example Output |
|----------|-------------|----------------|
| `{user.boost}` | Is boosting? | `Yes` or `No` |
| `{user.boost_since}` | Boost start date | `2024-01-15 12:30:45 UTC` |
| `{user.boost_since_timestamp}` | Boost Unix timestamp | `1705322445` |

---

## Server Variables

Information about the server.

| Variable | Description | Example Output |
|----------|-------------|----------------|
| `{guild}` | Server name | `My Server` |
| `{guild.name}` | Server name | `My Server` |
| `{guild.id}` | Server ID | `123456789012345678` |
| `{guild.count}` | Member count | `1500` |
| `{guild.owner_id}` | Owner's user ID | `123456789012345678` |
| `{guild.shard}` | Shard ID | `1` |
| `{guild.vanity}` | Vanity URL code | `myserver` or `N/A` |
| `{guild.preferred_locale}` | Server language | `en-US` |

### Server Assets

| Variable | Description | Example Output |
|----------|-------------|----------------|
| `{guild.icon}` | Server icon URL | `https://cdn.discordapp.com/...` |
| `{guild.banner}` | Server banner URL | `https://cdn.discordapp.com/...` or `N/A` |
| `{guild.splash}` | Invite splash URL | `https://cdn.discordapp.com/...` or `N/A` |
| `{guild.discovery}` | Discovery splash URL | `https://cdn.discordapp.com/...` or `N/A` |

### Server Stats

| Variable | Description | Example Output |
|----------|-------------|----------------|
| `{guild.emoji_count}` | Number of emojis | `50` |
| `{guild.role_count}` | Number of roles | `25` |
| `{guild.boost_count}` | Number of boosts | `14` |
| `{guild.boost_tier}` | Boost level | `2` or `N/A` |
| `{guild.key_features}` | Server features | `COMMUNITY, ANIMATED_ICON` |

### Server Channels

| Variable | Description | Example Output |
|----------|-------------|----------------|
| `{guild.channels_count}` | Total channels | `50` |
| `{guild.text_channels_count}` | Text channels | `30` |
| `{guild.voice_channels_count}` | Voice channels | `10` |
| `{guild.category_channels_count}` | Categories | `5` |
| `{guild.channels}` | Channel names (max 20) | `general, chat, media` |
| `{guild.text_channels}` | Text channel names | `general, chat, media` |
| `{guild.voice_channels}` | Voice channel names | `General, Music, Gaming` |
| `{guild.category_channels}` | Category names | `Text, Voice, Staff` |

### Server Limits

| Variable | Description | Example Output |
|----------|-------------|----------------|
| `{guild.max_members}` | Max member limit | `500000` |
| `{guild.max_presences}` | Max presences | `25000` |
| `{guild.max_video_channel_users}` | Max video users | `25` |
| `{guild.afk_timeout}` | AFK timeout (seconds) | `300` |
| `{guild.afk_channel}` | AFK channel name | `AFK` or `N/A` |

### Server Dates

| Variable | Description | Example Output |
|----------|-------------|----------------|
| `{guild.created_at}` | Server creation date | `2020-01-15 12:30:45 UTC` |
| `{guild.created_at_timestamp}` | Creation Unix timestamp | `1579091445` |

---

## Channel Variables

Information about the current channel.

| Variable | Description | Example Output |
|----------|-------------|----------------|
| `{channel.name}` | Channel name | `general` |
| `{channel.id}` | Channel ID | `123456789012345678` |
| `{channel.mention}` | Channel mention | `#general` |
| `{channel.topic}` | Channel topic | `Welcome to general chat!` |
| `{channel.type}` | Channel type | `text` |
| `{channel.position}` | Channel position | `5` |
| `{channel.slowmode_delay}` | Slowmode (seconds) | `0` |
| `{channel.category_id}` | Category ID | `123456789012345678` |
| `{channel.category_name}` | Category name | `Text Channels` |

---

## Date & Time Variables

Current date and time information.

### PST (Pacific Standard Time)

| Variable | Description | Example Output |
|----------|-------------|----------------|
| `{date.now}` | Current date | `2024-12-13` |
| `{date.now_proper}` | Full date | `December 13, 2024` |
| `{date.now_short}` | Short date | `Dec 13, 2024` |
| `{date.now_shorter}` | Shorter date | `12/13/24` |
| `{time.now}` | Current time | `03:45 PM` |
| `{time.now_military}` | 24-hour time | `15:45` |

### UTC

| Variable | Description | Example Output |
|----------|-------------|----------------|
| `{date.utc_now}` | UTC date | `2024-12-13` |
| `{date.utc_now_proper}` | UTC full date | `December 13, 2024` |
| `{date.utc_now_short}` | UTC short date | `Dec 13, 2024` |
| `{date.utc_now_shorter}` | UTC shorter date | `12/13/24` |
| `{time.utc_now}` | UTC time | `11:45 PM` |
| `{time.utc_now_military}` | UTC 24-hour time | `23:45` |
| `{date.utc_timestamp}` | Unix timestamp | `1702511100` |

---

## Using Timestamps

For Discord's dynamic timestamps, use the Unix timestamp variables with Discord's timestamp format:

```
<t:{user.joined_at_timestamp}:R>  → "2 months ago"
<t:{user.joined_at_timestamp}:F>  → "Friday, January 15, 2024 12:30 PM"
<t:{user.joined_at_timestamp}:D>  → "January 15, 2024"
```

**Timestamp Formats:**
| Format | Description | Example |
|--------|-------------|---------|
| `t` | Short time | `12:30 PM` |
| `T` | Long time | `12:30:45 PM` |
| `d` | Short date | `01/15/2024` |
| `D` | Long date | `January 15, 2024` |
| `f` | Short date/time | `January 15, 2024 12:30 PM` |
| `F` | Long date/time | `Friday, January 15, 2024 12:30 PM` |
| `R` | Relative | `2 months ago` |

---

## Examples

### Welcome Message
```
Welcome {user.mention} to **{guild.name}**! You are member #{guild.count}.
```

### User Info Embed
```
{embed}$v{title: {user.name}}$v{description: Joined: <t:{user.joined_at_timestamp}:R>}$v{thumbnail: {user.avatar}}$v{color: {user.color}}
```

### Server Stats
```
{embed}$v{title: {guild.name} Stats}$v{field: Members && {guild.count} && true}$v{field: Boosts && {guild.boost_count} && true}$v{field: Channels && {guild.channels_count} && true}
```


---

## Practical Examples

### Welcome Messages

**Simple welcome:**
```
Welcome {user.mention} to **{guild.name}**! 🎉
```

**With member count:**
```
Hey {user.mention}! You are member **#{guild.count}** in {guild.name}!
```

**With join date:**
```
Welcome {user.name}! You joined <t:{user.joined_at_timestamp}:R>.
```

**Full welcome embed:**
```
{embed}$v{author: Welcome to {guild.name}! && {guild.icon}}$v{description: Hey {user.mention}!\n\nYou are member **#{guild.count}**\nAccount created: <t:{user.created_at_timestamp}:R>}$v{thumbnail: {user.avatar}}$v{color: #00ff00}$v{footer: Enjoy your stay!}
```

---

### Leave Messages

**Simple leave:**
```
**{user.name}** has left the server. 👋
```

**With member count:**
```
{user.name} left. We now have **{guild.count}** members.
```

---

### Boost Messages

**Simple boost:**
```
🎉 **{user.name}** just boosted the server! Thank you!
```

**With boost count:**
```
{user.mention} boosted! We now have **{guild.boost_count}** boosts (Tier {guild.boost_tier})!
```

---

### User Info Display

**Profile card:**
```
{container}$v{section: # {user.display_name}\n-# @{user.name}\n\n**ID:** {user.id}\n**Created:** <t:{user.created_at_timestamp}:D>\n**Joined:** <t:{user.joined_at_timestamp}:R> && {user.avatar}}$v{separator}$v{text: **Top Role:** {user.top_role}\n**Color:** {user.color}}$v{color: {user.color}}
```

---

### Server Info Display

**Server stats:**
```
{embed}$v{author: {guild.name} && {guild.icon}}$v{field: Members && {guild.count} && true}$v{field: Channels && {guild.channels_count} && true}$v{field: Roles && {guild.role_count} && true}$v{field: Boosts && {guild.boost_count} (Tier {guild.boost_tier}) && true}$v{field: Emojis && {guild.emoji_count} && true}$v{field: Created && <t:{guild.created_at_timestamp}:D> && true}$v{thumbnail: {guild.icon}}$v{color: #5865F2}
```

---

### Autoresponder Examples

**Greeting:**
```
,ar add hi, Hello {user.name}! 👋 --not_strict
```

**Server info:**
```
,ar add serverinfo, {embed}$v{title: {guild.name}}$v{field: Members && {guild.count} && true}$v{field: Boosts && {guild.boost_count} && true}$v{thumbnail: {guild.icon}}$v{color: #5865F2}
```

**User info:**
```
,ar add whoami, {embed}$v{title: {user.name}}$v{description: **ID:** {user.id}\n**Joined:** <t:{user.joined_at_timestamp}:R>\n**Top Role:** {user.top_role}}$v{thumbnail: {user.avatar}}$v{color: {user.color}}
```

---

## Variable Categories Summary

| Category | Count | Examples |
|----------|-------|----------|
| User | 17 | `{user.name}`, `{user.mention}`, `{user.avatar}` |
| User Dates | 6 | `{user.created_at}`, `{user.joined_at_timestamp}` |
| User Boost | 3 | `{user.boost}`, `{user.boost_since}` |
| Server | 8 | `{guild.name}`, `{guild.count}`, `{guild.id}` |
| Server Assets | 4 | `{guild.icon}`, `{guild.banner}` |
| Server Stats | 5 | `{guild.boost_count}`, `{guild.emoji_count}` |
| Server Channels | 8 | `{guild.channels_count}`, `{guild.text_channels}` |
| Server Limits | 5 | `{guild.max_members}`, `{guild.afk_timeout}` |
| Server Dates | 2 | `{guild.created_at}`, `{guild.created_at_timestamp}` |
| Channel | 9 | `{channel.name}`, `{channel.mention}` |
| Date/Time PST | 6 | `{date.now}`, `{time.now}` |
| Date/Time UTC | 7 | `{date.utc_now}`, `{date.utc_timestamp}` |
| **Total** | **80+** | |
