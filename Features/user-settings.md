# User settings

## Introduction
Skuddbot features an user settings system. This allows to change parts of Skuddbot to their liking, and tailor their own experience with the bot.
Settings are saved on a per-server-basis, so it is possible for users to have settings set to different values in different servers.

## Available settings
| Setting Name                                                    | Technical Name       | Short Description                                                 | Value Type | Default Value | Cooldown |
|-----------------------------------------------------------------|----------------------|-------------------------------------------------------------------|------------|---------------|----------|
| [Level up notification](#level-up-notification)                 | `LEVEL_UP_NOTIFY`    | Defines how you are notified about level ups.                     | String     | REACTION      | None     |
| [Tracking enabled](#track-me)                                   | `TRACK_ME`           | Defines if the bot will track your statistics.                    | Boolean    | true          | None     |
| [Profile private](#profile-private)                             | `PROFILE_PRIVATE`    | Defines if your profile is private.                               | Boolean    | false         | None     |
| [Mention me](#mention-me)                                       | `MENTION_ME`         | Defines if you are mentioned in useless commands.                 | Boolean    | false         | None     |
| [Minigame reminders](#minigame-reminders)                       | `MINIGAME_REMINDERS` | Defines if you are reminded about outstanding minigames           | Boolean    | true          | None     |
| [Default bet](#default-bet)                                     | `DEFAULT_BET`        | Defines the default bet used in various minigames.                | Number     | 50            | None     |
| [Timezone](#timezone)                                           | `TIMEZONE`           | Defines your timezone, to offset different time based activities. | Number     | 0             | 24 hours |
| [Gender neutral playing cards](#gender-neutral-playingcards)    | `GN_PLAYING_CARDS`   | Defines whether you want to use gender neutral playing cards.     | Boolean    | true          | None     |
| [Appear anonymous in Game Logs](#appear-anonymous-in-game-logs) | `ANON_GAME_LOG`      | Defines whether the user will appear anonymized in the Game Logs  | Boolean    | false         | None     |

## Setting details
### Level up notification
Level up notification defines how a user is notified about a level up, this setting is restricted to the following values:
| Value      | Notification behaviour                         |
|------------|------------------------------------------------|
| `REACTION` | You are notified by reaction about a level up. |
| `MESSAGE`  | You are notified by message about a level up.  |
| `DM`       | You are notified in DM's about a level up.     |
| `NONE`     | You are not notified about level ups.          |
{% hint style="info" %}
* Reactions can be clicked to view a detailed message.  
* Server owners can disable the `MESSAGE` notification setting, for more information about the [allow message level up notification server setting](/Features/server-settings.md#allow-message-level-up-notification-type) view the [Server Settings](server-settings.md) article.
{% endhint %}

### Tracking enabled
This setting defines if Skuddbot tracks you. This includes all stats and currencies. If this is set to false, all progress will be paused, until this is turned back to true. You will still continue to show on leaderboards, regardless of what this setting is set to.

### Profile private
This setting defines if others are able to see your stats and currencies. When set to true, only you and people with Server Admin permissions can ask the bot for your stats. If you ask for your stats/profile, other people can still see it.
{% hint style="info" %}
For more information about permissions, view the [Permissions](/Systems/permissions.md) article.
{% endhint %}

### Mention me
This setting defines if you are mentioned in useless commands, these are commands like `!hug` and `!punch`.
{% hint style="info" %}
For more information about useless commands, view the [Useless Commands](/Commands/useless-commands.md) article.
{% endhint%}

### Minigame reminders
This setting defines if you are reminded about outstanding minigames. When enabled, you are sent reminders in DM.
This currently applies to the following minigames:
* [Free for All](/Minigames/free-for-all.md)

### Default bet
This setting defines what the bet of the user will be when they don't specify a bet when starting the minigame. This setting currently applies to the following minigames:
* [Double or Nothing](/Minigames/double-or-nothing.md)
* [Free for All](/Minigames/free-for-all.md)
* [Challenge](/Minigames/challenge.md)
* [Blackjack](/Minigames/blackjack.md)

### Timezone
The user can define their timezone to offset certain time based activities to their timezone. This setting only takes values between -12 and +12. This setting can also only be changed once every 24 hours.
This setting currently applies to the following activities:
* [Daily bonus](/Systems/daily-bonus.md)

{% hint style="success" %}
To figure out what your offset is, you can use the list of timezones on [timeanddate.com](https://www.timeanddate.com/time/zones/). Find your timezone in the table and see your offset in the right-most colum.
{% endhint %}
{% hint style="warning" %}
When changing this setting, enter negative numbers as `-12` and positive numbers as `12` (no plus sign).
{% endhint %}

### Gender neutral playing cards
When this setting is set to `true`, the ranks jack, queen and king, are replaced by bronze, silver and gold in minigames that use playing cards.
This setting currently applies to the following minigames:
* [Blackjack](/Minigames/blackjack.md)

### Appear anonymous in Game Logs
When a user does not want to appear with their name in the Game Logs, they can set this setting to `true`. This will make their name(s) appear anonymized in the Game Logs.
{% hint style="info" %}
For more information about [anonymized usernames in Game Logs](/Minigames/game-logs.md#anonymized-usernames), view the [Game Logs](/Minigames/game-logs.md) article.
{% endhint %}

## Command
The command for viewing and editing user settings is: `!usersettings`.   
This command also listens to the following aliases: 
- `!usettings`

#### Command parameters
| Parameter | Type   | Description                                       | Required? |
|-----------|--------|---------------------------------------------------|-----------|
| Setting   | String | This defines the setting you want to view/edit.   | No        |
| Value     | Any    | This is the new value the setting will be set to. | No        |

#### Command examples
| Example                         | Action                                                      | Response                                                       |
|---------------------------------|-------------------------------------------------------------|----------------------------------------------------------------|
| `!usersettings`                 | Simplest form, shows all settings and their current value.  | A table with all settings and their current value.             |
| `!usersettings MENTION_ME`      | Views more detailed information about `MENTION_ME` setting. | A list of detailed infromation about the `MENTION_ME` setting. |
| `!usersettings MENTION_ME true` | Updates the setting `MENTION_ME` to `true`.                 | ✅ reaction to the message.                                     |
{% hint style="info" %}
Reactions can be clicked to get a more detailed response.
{% endhint %}

#### Permission requirements
This command requires no permissions.
{% hint style="info" %}
For more information about permissions, view the [Permissions](/Systems/permissions.md) article.
{% endhint %}
