# Server settings

## Introduction
Skuddbot features an server settings. This allows server owners to change parts of Skuddbot to their liking and tailor their own Skuddbot experience for their server. 

## Available settings
| Setting name                                                                              | Technical name               | Short description                                                                  | Category          | Value type                | Default value        |
|-------------------------------------------------------------------------------------------|------------------------------|------------------------------------------------------------------------------------|-------------------|---------------------------|----------------------|
| [Minimun experience gained](#gaining-experience)                                          | `XP_MIN`                     | Defines the minimum amount of experience gained per message.                       | `XP`              | Number                    | 10                   |
| [Maximum experience gained](#gaining-experience)                                          | `XP_MAX`                     | Defines the maximum amount of experience gained per message.                       | `XP`              | Number                    | 15                   |
| [~~Minimun experience gained on twitch~~](#gaining-experience)                            | `XP_MIN_TWITCH`              | Defines the minimum amount of experience gained per message on Twitch.             | `XP`              | Number                    | 10                   |
| [~~Maximum experience gained on twitch~~](#gaining-experience)                            | `XP_MAX_TWITCH`              | Defines the maximum amount of experience gained per message on Twitch.             | `XP`              | Number                    | 15                   |
| [Experience base value](#leveling-curve)                                                  | `XP_BASE`                    | Defines how much experience an user needs to level up from level one to level two. | `XP`              | Number                    | 1500                 |
| [Experience multiplier](#leveling-curve)                                                  | `XP_MULTIPLIER`              | Defines how steep the experience leveling curve is.                                | `XP`              | Number with decimal place | 1.2                  |
| [~~Twitch channel~~](#twitch-channel)                                                     | `TWITCH_CHANNEL`             | Defines what Twitch channel the bot is in.                                         | `TWITCH`          | String                    | null                 |
| [Welcome message](#welcome-and-goodbye-messages)                                          | `WELCOME_MESSAGE`            | Defines the message that will be posted when a user joins the server.              | `WELCOME_GOODBYE` | String                    | null                 |
| [Goodbye message](#welcome-and-goodbye-messages)                                          | `GOODBYE_MESSAGE`            | Defines the message that will be posted when a user leaves the server.             | `WELCOME_GOODBYE` | String                    | null                 |
| [Welcome and goodbye messages channel](#welcome-and-goodbye-messages)                     | `WELCOME_GOODBYE_CHANNEL`    | Defines the channel where the welcome and goodbye messages will be posted.         | `WELCOME_GOODBYE` | Number (of: channel ID)   | -1                   |
| [Admin role](#granting-admin-permissions)                                                 | `ADMIN_ROLE`                 | Defines which role should be given server admin permissions in the bot.            | `DISCORD`         | String (of: role name)    | nulll                |
| [Grant role on join](#granting-a-role-on-join)                                            | `ROLE_ON_JOIN`               | Defines what role will be given to users that join the server.                     | `DISCORD`         | String (of: role name)    | null                 |
| [Allow message level up notification type](#allow-message-level-up-notification-type)     | `ALLOW_MSG_LVL_UP_NOTIFY`    | Defines if the message level up notification type is allowed.                      | `DISCORD`         | Boolean                   | true                 |
| [Arena name](#arena-name)                                                                 | `ARENA_NAME`                 | Defines the name of the arena mentioned in various minigames.                      | `MINIGAMES`       | String                    | Skuddbot's Colosseum |
| [Jackpot](/Systems/jackpot.md)                                                            | `JACKPOT`                    | Defines the Jackpot amount.                                                        | `MINIGAMES`       | Number                    | 0                    |
| [Command prefix](#command-prefix)                                                         | `COMMAND_PREFIX`             | Defines the prefix for commands.                                                   | `COMMANDS`        | String                    | !                    |
| [Allowing multiple images in image commands](#allowing-multiple-images-in-image-commands) | `ALLOW_MULTI_IMG`            | Defines if using a image command may display multiple images.                      | `COMMANDS`        | boolean                   | false                |
| [Daily currency bonus](#daily-bonuses)                                                    | `DAILY_CURRENCY_BONUS`       | Defines the base amount of the daily currency bonus.                               | `DAILY_BONUS`     | Number                    | 100                  |
| [Daily experience bonus](#daily-bonus)                                                    | `DAILY_EXPERIENCE_BONUS`     | Defines the base amount of the daily experience bonus.                             | `DAILY_BONUS`     | Number                    | 250                  |
| [Daily bonus multiplier](#daily-bonus)                                                    | `DAILY_BONUS_MODIFIER`       | Defines the mulitplier of the daily bonus amounts.                                 | `DAILY_BONUS`     | Number with decimal place | 1.05                 |
| [Daily bonus cap](#daily-bonus)                                                           | `DAILY_BONUS_MULTIPLIER_CAP` | Defines after how many days the multiplier will cap out.                           | `DAILY_BONUS`     | Number                    | 30                   |

## Setting details
### Experience settings
#### Gaining experience
The settings `XP_MIN` and `XP_MAX` control the amount of experience a user gains per message, a random amount is picked between these values and added to the users experience total. The `XP_MIN_TWITCH` and `XP_MAX_TWITCH` settings do the same thing but for Twitch.
{% hint style="warning" %}
Twitch support is currently under development.
{% endhint %}

#### Leveling curve
The settings`XP_BASE` and `XP_MULTIPLIER` control the leveling curve. These two values are put into a formula to calculate how much experience a user needs to level up.
{% hint style="info" %}
For more information about experience, please view the [Experience](/Systems/experience.md) article.
{% endhint %}

### Twitch channel
This defines what Twitch channel the bot is in. It will track stats there for the server this setting applies to.
{% hint style="warning" %}
Twitch support is currently under development.
{% endhint %}

### Welcome and goodbye messages
The `WELCOME_MESSAGE` and `GOODBYE_MESSAGE` settings control the message format of their respective event. These formats can contain 2 variables:  
* `$name` - Will be replaced by the name of the user that joins or leaves the server.
* `$server` - Will be replaced by the name of the server that is joined/left.

`WELCOME_GOODBYE_CHANNEL` takes a ID of a channel for these messages to be posted in, this setting must be set in order for the welcome and goodbye messages to work.

#### Channel does not exist error
Server owners can receive a DM from Skuddbot about that the bot tried to send a welcome/goodbye message to a channel that does not exist. When this error is encountered, the bot will automatically set the `WELCOME_GOODBYE_CHANNEL` value to `-1` (disabled). To reactivate, a user with the `SERVER_ADMIN` permission, must set the `WELCOME_GOODBYE_CHANNEL` setting back to a channel ID that does exist.  
{% hint style="info" %}
* For more information about getting ID's of things in Discord, please view [Turning on developer mode](/getting-started.md#turning-on-developer-mode) in the [Getting started](/getting-started.md) article.  
* For more information about permissions, view the [Permissions](/Systems/permissions.md) article.
{% endhint %}

### Granting admin permissions
The `ADMIN_ROLE` setting takes a name of a role,  people that have this role will be granted the `SERVER_ADMIN` permission.
{% hint style="success" %}
It's good practice to make a separate role, with no permission nodes enabled within Discord. Then set the setting to the name of this role. This way you have more fine control over who has admin permission within Skuddbot, by simply assigning the role to people you want to have this permission level.
{% endhint %}
{% hint style="info" %}
For more information about permissions, view the [Permissions](/Systems/permissions.md) article.
{% endhint %}
{% hint style="danger" %}
Make sure the role name is typed exactly as it is set in Discord. This setting is case sensitive.
{% endhint %}

### Granting a role on join
The `ROLE_ON_JOIN` setting takes the name of a role, this role will be given to users when they join the server.
Setting this setting to `null` disables it.
{% hint style="danger" %}
* Make sure the role name is typed exactly as it is set in Discord. This setting is case sensitive.
* Make sure the role you are trying to give is below the highest role Skuddbot has in the hierarchy.
{% endhint %}

### Allow message level up notification type
This setting allows or disallows the use of the `MESSAGE` level up notification type. When set to `false`, any user that has set it's notification setting set to `MESSAGE` will be defaulted to `REACTION`.
{% hint style="info" %}
For more information about the [Level up notification user setting](user-settings.md#level-up-notification), view the [User settings](user-settings.md) article.
{% endhint %}

### Arena name
The `ARENA_NAME` setting defines the name of the arena that will be mentioned in various minigames.
Currently this setting applies to the following minigames:
* [Challenge](/Minigames/challenge.md)

### Command prefix
This setting can be used to change the prefix of the commands that the bot listens to, this can be useful to prevent it conflicting with other bots.
Prefixes also support spaces, please use `_` (underscores) to denote spaces while setting this setting. If you set the prefix to `skuddbot_`, the bot will listen to commands that look like `skuddbot ping`.
{% hint style="warning" %}
* Sometimes the bot might still show the default prefix when showing commands in Discord, if this happens, please [contact me](/Help/contact.md) to get this updated.
* Commands on this wiki will always show `!` as their prefix.
{% endhint %}

### Allowing multiple images in image commands
This setting defines if users are allowed to request multiple images from the image commands at once. When set to `true`, this will allow users to request up to a maximum of 5 images per command. When set to `false` a user may still specify a number, but it will be defaulted to 1.
{% hint style="info" %}
For more information about image commands, please refer to the [Image commands](/Commands/image-commands.md) article.
{% endhint %}

### Daily bonuses
The daily bonus settings define how much bonuses each user can claim each day. Bonuses scale exponentially based on how many days a user claims their bonus in a row.
{% hint style="info" %}
For more information about daily bonuses, check the [Daily bonus](/Systems/daily-bonus.md) article.
{% endhint %}

## Command
The command for viewing and editing server settings is: `!serversettings`.   
This command also listens to the following aliases: 
- `!ssettings`

#### Command parameters
| Parameter | Type   | Description                                       | Required? |
|-----------|--------|---------------------------------------------------|-----------|
| Setting   | String | This defines the setting you want to view/edit.   | No        |
| Value     | Any    | This is the new value the setting will be set to. | No        |

#### Command examples
| Example                               | Action                                                        | Response                                                         |
|---------------------------------------|---------------------------------------------------------------|------------------------------------------------------------------|
| `!serversettings`                     | Simplest form, shows all settings and their current value.    | A table with all settings and their current value.               |
| `!serversettings ROLE_ON_JOIN`        | Views more detailed information about `ROLE_ON_JOIN` setting. | A list of detailed infromation about the `ROLE_ON_JOIN` setting. |
| `!serversettings ROLE_ON_JOIN Member` | Updates the setting `ROLE_ON_JOIN` to `Member`.               | ✅ reaction to the message.                                       |
{% hint style="info" %}
Reactions can be clicked to get a more detailed response.
{% endhint %}

#### Pages
When viewing all settings, users may use the ![](https://i.imgur.com/3pFjjWm.png) and ![](https://i.imgur.com/DkZ1fXh.png) reactions to navigate between pages. Users may use the ![](https://i.imgur.com/yIDl5mz.png) reaction to refresh the page.
Buttons disappear after 10 minutes.

#### Permission requirements
This command requires the `SERVER_ADMIN` permission.
{% hint style="info" %}
For more information about permissions, view the [Permissions](/Systems/permissions.md) article.
{% endhint %}