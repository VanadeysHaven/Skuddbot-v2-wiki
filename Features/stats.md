# Stats

## Introduction
Skuddbot features a stats system, where all kinds of statistics about the user are tracked. Users can build up their statistics by chatting and playing minigames.

## Available stats
| Stat Name                                                             | Technical Name                | Tracks                                                                                       | Leaderboard? | Editable? |
|-----------------------------------------------------------------------|-------------------------------|----------------------------------------------------------------------------------------------|--------------|-----------|
| [Experience](/Systems/experience.md)                                  | `EXPERIENCE`                  | The user's experience amount.                                                                | Yes          | Yes       |
| [Challenge wins](/Minigames/challenge.md)                             | `CHALLENGE_WINS`              | The amount of wins the user has gotten in Challenge.                                         | Yes          | Yes       |
| [Challenge losses](/Minigames/challenge.md)                           | `CHALLENGE_LOSSES`            | The amount of losses the user has gotten in Challenge.                                       | Yes          | Yes       |
| [Challenge winstreak](/Minigames/challenge.md)                        | `CHALLENGE_WINSTREAK`         | The current Challenge winstreak of the user.                                                 | Yes          | Yes       |
| [Challenge longest winstreak](/Minigames/challenge.md)                | `CHALLENGE_LONGEST_WINSTREAK` | The longest Challenge winstreak of the user.                                                 | Yes          | Yes       |
| [Challenge bets won](/Minigames/challenge.md)                         | `CHALLENGE_BETS_WON`          | The amount of bets the user has won in challenge.                                            | Yes          | Yes       |
| [Challenge bets lost](/Minigames/challenge.md)                        | `CHALLENGE_BETS_LOST`         | The amount of bets the user has lost in challenge.                                           | Yes          | Yes       |
| [Free for All wins](/Minigames/free-for-all.md)                       | `FFA_WINS`                    | The amount of wins the user has gotten in Free for All.                                      | Yes          | Yes       |
| [Free for All losses](/Minigames/free-for-all.md)                     | `FFA_LOSSES`                  | The amount of losses the user has gotten in Free for All.                                    | Yes          | Yes       |
| [Free for All highest entrants win](/Minigames/free-for-all.md)       | `FFA_HIGHEST_WIN`             | The highest amount of people entered into a FFA the user has won.                            | Yes          | Yes       |
| [Free for All kills](/Minigames/free-for-all.md)                      | `FFA_KILLS`                   | The amount of kills the user has gotten in Free for All .                                    | Yes          | Yes       |
| [Free for All bets won](/Minigames/free-for-all.md)                   | `FFA_BETS_WON`                | The amount of bets the user has won in Free for All.                                         | Yes          | Yes       |
| [Free for All bets lost](/Minigames/free-for-all.md)                  | `FFA_BETS_LOST`               | The amount of bets the user has lost in Free for All.                                        | Yes          | Yes       |
| [Blackjack wins](/Minigames/blackjack.md)                             | `BJ_WINS`                     | The amount of hands the user has won in Blackjack.                                           | Yes          | Yes       |
| [Blackjack losses](/Minigames/blackjack.md)                           | `BJ_LOSSES`                   | The amount of hands the user has lost in Blackjack.                                          | Yes          | Yes       |
| [Blackjack pushes](/Minigames/blackjack.md)                           | `BJ_PUSHES`                   | The amount of hands the user has pushed in Blackjack.                                        | Yes          | Yes       |
| [Blackjack 21's](/Minigames/blackjack.md)                             | `BJ_TWENTY_ONES`              | The amount of 21's the user has gotten in Blackjack.                                         | Yes          | Yes       |
| [Blackjack Blackjack's](/Minigames/blackjack.md)                      | `BJ_BLACKJACKS`               | The amount of Blackjacks the user has gotten.                                                | Yes          | Yes       |
| [Blackjack Double Down Wins](/Minigames/blackjack.md)                 | `BJ_DD_WINS`                  | The amount of doubled down hands the user has won in Blackjack.                              | Yes          | Yes       |
| [Blackjack Double Down Pushes](/Minigames/blackjack.md)               | `BJ_DD_PUSHES`                | The amount of doubled down hands the user has pushed in Blackjack.                           | Yes          | Yes       |
| [Blackjack Double Down Losses](/Minigames/blackjack.md)               | `BJ_DD_LOSSES`                | The amount of doubled down hands the user has lost in Blackjack.                             | Yes          | Yes       |
| [Team Deathmatch wins](/Minigames/team-deathmatch.md)                 | `TD_WINS`                     | The amount of wins the user has gotten in Team Deathmatch.                                   | Yes          | Yes       |
| [Team Deathmatch losses](/Minigames/team-deathmatch.md)               | `TD_LOSSES`                   | The amount of losses the user has gotten in Team Deathmatch                                  | Yes          | Yes       |
| [Team Deathmatch defences](/Minigames/team-deathmatch.md)             | `TD_DEFENCES`                 | The amount of times a user has saved a teammate from dying in Team Deathmatch.               | Yes          | Yes       |
| [Team Deathmatch highest win](/Minigames/team-deathmatch.md)          | `TD_HIGHEST_WIN`              | The highest amount of people entered into Team Deathmatch the user has won.                  | Yes          | Yes       |
| [Team Deathmatch entire time survived](/Minigames/team-deathmatch.md) | `TD_ALL_SURIVED`              | The amount of times the entire team the user was a part of has survived.                     | Yes          | Yes       |
| [Team Deathmatch kills](/Minigames/team-deathmatch.md)                | `TD_KILLS`                    | The amount of kills the user has gotten in Team Deathmatch.                                  | Yes          | Yes       |
| [Team Deathmatch favourite teammate](/Minigames/team-deathmatch.md)   | `TD_TEAMMATES`                | The teammate(s) the user has teamed up with the most.                                        | No           | No        |
| [Daily Bonus current streak](/Systems/daily-bonus.md)                 | `DAILY_CURRENT_STREAK`        | The current claim streak of the daily bonus the user is on.                                  | Yes          | Yes       |
| [Daily Bonus multiplier](/Systems/daily-bonus.md)                     | `    DAILY_CURRENT_MULTIPLIER`            | The current multiplier of the user that will be applied to their bonus.                      | No           | Yes       |
| [Daily Bonus days frozen](/Systems/daily-bonus.md)                    | `DAILY_DAYS_FROZEN`           | The amount of days the user has misse                                                        | No           | Yes       |
| [Daily Bonus longest streak](/Systems/daily-bonus.md)                 | `DAILY_LONGEST_STREAK`        | The longest claim streak of the daily bonus the user has had.                                | Yes          | Yes       |
| [Double or Nothing wins](/Minigames/double-or-nothing.md)             | `DON_WINS`                    | The amount wins the user has gotten in Double or Nothing.                                    | Yes          | Yes       |
| [Double or Nothing losses](/Minigames/double-or-nothing.md)           | `DON_LOSSES`                  | The amount of losses the user has gotten in Double or Nothing                                | Yes          | Yes       |
| [Double or Nothing longest streak](/Minigames/double-or-nothing.md)   | `DON_LONGEST_STREAK`          | The higest amount of times the user has managed to double up within one game wihtout losing. | Yes          | Yes       |

## Categories
| Category          | Technical Name      |
|-------------------|---------------------|
| No category       | `NO_CATEGORY`       |
| Challenge         | `CHALLENGE`         |
| Free for All      | `FREE_FOR_ALL`      |
| Blackjack         | `BLACKJACK`         |
| Team Deathmatch   | `TEAM_DEATHMATCH`   |
| Daily Bonus       | `DAILY_BONUS`       |
| Double or Nothing | `DOUBLE_OR_NOTHING` |

## Earning stats
{% hint style="info" %}
For information on how to earn stats please refer to the article of the minigame/system.
{% endhint %}

## Commands
### View and edit
The command for viewing and editing stats is `!stats`.

#### Command parameters
##### Viewing
| Parameter         | Type             | Description                                                               | Required? |
|-------------------|------------------|---------------------------------------------------------------------------|-----------|
| User ID / Mention | Number / Mention | Specifies the user to be shown, defaults to the user running the command. | No        |

##### Editing
| Parameter          | Type             | Description                                                                                                                            | Required? |
|--------------------|------------------|----------------------------------------------------------------------------------------------------------------------------------------|-----------|
| User ID / Mention  | Number / Mention | Specifies the user to be edited.                                                                                                       | Yes       |
| Stat               | String           | The techinical name of the stat to be edited. - Is automatically set to upper case and dashes `(-)` are replaced by underscores `(_)`. | Yes       |
| Add / Remove / Set | String           | The operation to be carried out. - Can be `add`, `remove` or `set`.                                                                    | Yes       |
| Amount             | Number           | The amount for the operation to be carried out with.                                                                                   | Yes       |

#### Command examples
##### Viewing
| Example                     | Action                                     | Response                                        |
|-----------------------------|--------------------------------------------|-------------------------------------------------|
| `!stats`                    | Simplest form, shows the user's own stats. | Embed with the user's own stats.                |
| `!stats @MyNameIsDave#0001` | Shows the stats of user MyNameIsDave#0001. | Embed with the stats of user MyNameIsDave#0001. |
| `!stats 01234`              | Shows stats of the user with ID 01234.     | Embed with the stats of the user with ID 01234. |

##### Editing
| Example                                         | Action                                                             | Response                   |
|-------------------------------------------------|--------------------------------------------------------------------|----------------------------|
| `!stats @MyNameIsDave#0001 FFA_WINS add 10`     | Adds 10 to the FFA_WINS stat of user MyNameIsDave#0001.            | ✅ reaction to the message  |
| `!stats 01234 CHALLENGE_WINS remove 10`         | Removes 10 from the CHALLENGE_WINS stat of the user with id 01234. | ✅ reaction to the message. |
| `!currency @MyNameIsDave#0001 BJ_LOSSES set 10` | Sets the BJ_LOSSES stat of user MyNameIsDave#0001 to 10.           | ✅ reaction to the message. |

{% hint style="info" %}
Reactions can be clicked to get a more detailed response.
{% endhint %}

#### Permission requirements
| Operation                                                         | Required permissions    |
|-------------------------------------------------------------------|-------------------------|
| Viewing the user's own stats.                                     | No permissions required |
| Viewing someone else's stats.                                     | No permissions required |
| Viewing someone else's stats, who has made their profile private. | Server Admin            |
| Editing your own, or someone else's stats.                        | Server Admin            |

{% hint style="info" %}
* For more information on permissions, view the [Permissions](/Systems/permissions.md) article.  
* For more information about making your profile private, view the [profile private user setting](user-settings.md#profile-private) in the [User Settings](user-settings.md) article.
{% endhint %}

#### Pages while viewing
The stats command makes use of pages while viewing all stats. The user may use the ![](https://i.imgur.com/3pFjjWm.png) and ![](https://i.imgur.com/DkZ1fXh.png) reactions to navigate between pages. By pressing the ![](https://i.imgur.com/yIDl5mz.png) reaction the page can be refreshed.

##### Paging logic
The pages are divided into the categories as they are described in the [categories](#categories) section. Categories will be merged into 1 page if they don't exceed the limit of 21. Categories are not split, unless a category has more than 21 stats, then that category will be divided into multiple pages.

### Leaderboards
The command for viewing stat leaderboards is: `!statleaderboard`.
This command also listens to the following aliases:
- `!slb`
- `!statlb`

#### Command parameter
| Parameter   | Type             | Description                                                                                       | Required? |
|-------------|------------------|---------------------------------------------------------------------------------------------------|-----------|
| Stat / List | String / Keyword | This parameter takes a technical name of a stat. - Can also be `list` to list all avaiable stats. | No        |

#### Command examples
| Example                           | Action                                         | Response                                       |
|-----------------------------------|------------------------------------------------|------------------------------------------------|
| `!statleaderboard CHALLENGE_WINS` | Shows the CHALLENGE_WINS currency leaderboard. | A message with the CHALLENGE_WINS leaderboard. |
| `!statleaderboard list`           | Lists the available stats.                     | A message with the available stats.            |

#### Command permissions
This command requires no permissions.
{% hint style="info" %}
For more information on permissions, view the [Permissions](/Systems/permissions.md) article.  
{% endhint %}