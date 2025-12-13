---
description: Donator perks are rewards given to those who choose to donate to Adore.
icon: sack-dollar
---

# Donator perks

### How to obtain Donator Perks

Donator perks can be purchased via a small donation to keep the bot running free to everyone.

You can create a [ticket on our server](https://discord.gg/adore) if you like the project and want to donate.

---

## Donator Commands

These commands are exclusive to users with donator status.

### Self Prefix

Set a personal prefix that works across all servers.

| Command | Description | Syntax |
|---------|-------------|--------|
| `selfprefix set` | Set a custom prefix for yourself | `selfprefix set (prefix)` |
| `selfprefix remove` | Remove your personal prefix | `selfprefix remove` |

**Example:**
```
,selfprefix set ;
```
Now you can use `;ban @user` instead of `,ban @user` in any server.

---

### Self Alias

Create personal command shortcuts that work across all servers.

| Command | Description | Syntax |
|---------|-------------|--------|
| `selfalias add` | Add a shortcut alias for a command | `selfalias add (shortcut) (command)` |
| `selfalias remove` | Remove a specific alias | `selfalias remove (shortcut)` |
| `selfalias removeall` | Remove all aliases for a command | `selfalias removeall (command)` |
| `selfalias view` | View what command an alias maps to | `selfalias view (shortcut)` |
| `selfalias list` | List all your donator aliases | `selfalias list` |
| `selfalias reset` | Remove all your donator aliases | `selfalias reset` |

**Example:**
```
,selfalias add k kick
,selfalias add b ban
```
Now you can use `,k @user` to kick and `,b @user` to ban.

{% hint style="info" %}
You can have up to **50 personal aliases** as a donator.
{% endhint %}
