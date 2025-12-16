# Command Flags

Flags are optional parameters you can add to certain commands to modify their behavior.

---

## Flags Overview

| Flag | Description | Default |
|------|-------------|---------|
| `--mention` | Allows @mentions to actually ping users | Off |
| `--self_destruct` | Deletes the bot's response after X seconds | 5 seconds |
| `--delete` | Deletes the user's trigger message | Off |
| `--reply` | Replies to the trigger message | Off |
| `--not_strict` | Trigger can appear anywhere in message | Off (exact match) |
| `--cooldown` | Per-user cooldown before trigger works again | 5 seconds |
| `--role` | Only trigger for users with this role | None |
| `--ignore` | Don't trigger for users with this role | None |

---

## Command Support

| Command | Supported Flags |
|---------|-----------------|
| autoresponder | `--mention` `--self_destruct` `--delete` `--reply` `--not_strict` `--cooldown` `--role` `--ignore` |
| stickymessage | `--mention` `--reply` `--role` `--ignore` |
| welcome | `--mention` `--self_destruct` |
| leave | `--mention` `--self_destruct` |
| boost | `--mention` `--self_destruct` |

---

## Flag Details

### --mention
Allows @mentions in the message to actually ping users. By default, mentions are suppressed.

### --self_destruct
Schedules the bot's response for deletion. Time: 5-60 seconds.
```
--self_destruct        (deletes after 5 seconds)
--self_destruct 30     (deletes after 30 seconds)
```

### --delete
Deletes the user's trigger message after the response is sent.

### --reply
Replies to the trigger message instead of sending a standalone message.

### --not_strict
Searches for the trigger anywhere in the message. Example: trigger `hello` will respond to `hello there`.

### --cooldown
Sets a per-user cooldown. Time: 5-300 seconds.
```
--cooldown             (5 second cooldown)
--cooldown 10          (10 second cooldown)
```

### --role
Only activates for users with the specified role. Supports role mentions, IDs, or names.
```
--role @Verified
--role 123456789
--role Verified
```

### --ignore
Won't activate for users with the specified role. Supports role mentions, IDs, or names.
```
--ignore @Staff
--ignore 123456789
--ignore Staff
```
