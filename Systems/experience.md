# Experience
## Introduction
Skuddbot features an experience system. Uses can gain experience and level up. 

## Gaining experience
### Minigames
Users can play minigames in Skuddbot which will allow them to gain experience. The amount a user will gain is based on the minigame and the performance of the user.
Currently the following minigames award experience:
* [Blackjack](/Minigames/blackjack.md)
* [Challenge](/Minigames/challenge.md)
* [Double or Nothing](/Minigames/double-or-nothing.md)
* [Free For All](/Minigames/free-for-all.md)

### Chatting
A user will gain a random amount of experience between a set minimum and maximum value per message they post. These minimum and maximum values can be set by the server admins using the `!serversettings` command.
{% hint style="info" %}
For more information about [controlling experience gain](/Features/server-settings.md#gaining-experience), view the [Server settings](/Features/server-settings.md) article.
{% endhint %}

### Claiming daily bonus
A user can get a bonus amount of experience every day by claiming their daily bonus!
{% hint style="info" %}
For more information about daily bonuses, view the [Daily bonus](/Systems/daily-bonus.md) article.
{% endhint %}

## Leveling up
{% hint style="danger" %}
**WARNING:** Heavy math ahead.
{% endhint %}
Levels in Skuddbot scale exponentially. Skuddbot calculates levels using the `XP_BASE` and `XP_MULTIPLIER` settings. The `XP_BASE` setting defines how much experience a user needs to level up from level 1 to level 2. The `XP_MULTIPLIER` setting defines how quickly the amount of experience rises per level. Skuddbot uses the following formula to calculate the experience required to level up:
![](https://i.imgur.com/NuDiaX7.png)
{% hint style="info" %}
For more information about [controlling the leveling curve](/Features/server-settings.md#leveling-curve), view the [Server settings](/Features/server-settings.md) article.
{% endhint %}

### Calculating an user's level
An users level is calculated with the following steps:  
1. Starting at level 1, subtract the experience required to level up from the user's experience amount. Keep repeating, while incrementing the level, until there's less experience left than is required to level up.  
2. Divide the experience left by the amount required to level up, and multiply by 100. This is the user's level progress.  

## Viewing an user's level
The command for viewing an user's level information is: `!experience`.
This command also listens to the following aliases:
* `!xp`

#### Command parameters
| Parameter         | Type             | Description                                                       | Required? |
|-------------------|------------------|-------------------------------------------------------------------|-----------|
| User ID / Mention | Number / Mention | Specifies the user to view, defaults to user running the command. | No        |

#### Command examples
| Example                          | Action                                                     | Response                                                            |
|----------------------------------|------------------------------------------------------------|---------------------------------------------------------------------|
| `!experience`                    | Simplest form, shows the user's own level information.     | A message with the user's own level information.                    |
| `!experience @MyNameIsDave#0001` | Shows the level information of the user MyNameIsDave#0001. | A message with the level information of user MyNameIsDave#0001.     |
| `!experience 01234`              | Shows the level information of the user with the ID 01234. | A message with the level infromation of the user with the ID 01234. |
{% hint style="info" %}
* You can also view level's using the [Stats command](/Features/stats.md).
* Experience can be edited using the [Stats command](/Features/stats.md).
{% endhint %}

#### Permission requirements
| Action                                                                        | Required permission     |
|-------------------------------------------------------------------------------|-------------------------|
| Viewing the user's own level information.                                     | No permissions required |
| Viewing someone else's level information                                      | No permissions required |
| Viewing someone else's level information, who has made their profile private. | Server Admin            |
{% hint style="info" %}
* For more information on permissions, view the [Permissions](/Systems/permissions.md) article.  
* For more information about making your profile private, view the [profile private user setting](user-settings.md#profile-private) in the [User Settings](user-settings.md) article.
{% endhint %}

