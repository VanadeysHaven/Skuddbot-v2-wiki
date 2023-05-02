# Challenge

## Introduction
Challenge is a minigame where users can challenge each other to a one on one battle. The winner is chosen at random and is rewarded with experience. Users can also place bets.

## Game flow
### Starting a fight
A challenge is started by either challenging another user to a fight or by starting an open fight.

#### Inviting another user
To invite another user, the user types the command `!challenge <mention> [bet]`. Where `<mention>` is replaced with a mention of another user. And `[bet]` is the bet the user wants to place, sepcifying a bet is optional, this defaults to the user's `DEFAULT_BET` setting.
This mention may be any user, except bots and the user themselves. This fight can only be accepted by the invited user.

#### Starting a open fight
To start a open fight, the user types the command `!challenge open [bet]`. This fight can be accepted by any user, except the user themselves. The user may optionally specify a bet, this defaults to the user's `DEFAULT_BET` setting.

{% hint style="info" %}
* For more information about the [default bet](/Features/user-settings.md#default-bet), view the [user settings](/Features/user-settings.md) article.
* For more information about the betting system, view the [betting system](#betting-system) section.
* For more information about the command, view the [commands](#commands) section.
{% endhint %}

### Accepting a fight
A fight can be accepted in 2 ways. When a fight is accepted it will immediately start, the results are revealed after 5 seconds.

#### Using commands
A user can accept a fight by using the `!challenge <mention>` command, where they mention a user that has either invited them or has a open challenge standing out.

#### Using reactions
A user can accept a fight by clicking the ![](https://i.imgur.com/yp4rWf2.png) reaction, on a challenge that either is for them or is a open challenge.

### Declining a fight
{% hint style="danger" %}
A open fight cannot be declined.
{% endhint %}

#### Using commands
A user can decline a fight by using commands by typing `!challenge <mention> decline`, where they mention a user that has invited them to a challenge.

#### Using reactions
A user can delcine a fight by clicking the ![](https://i.imgur.com/n2UfbMz.png) reaction, on a challenge that is for them.

### Canceling a fight
#### Using commands
The user that has started a fight can cancel their fight using the `!challenge cancel` command.

#### Using reactions
The user that has started a fight can cancel their fight using the ![](https://i.imgur.com/n2UfbMz.png) reaction.

### Post Game
After 5 seconds after the fight has been accepted, the results are revealed and the rewards are awarded.

## Stats
| Stats             | Technical name                | Tracks                                                   | Awarded                                                     |
|-------------------|-------------------------------|----------------------------------------------------------|-------------------------------------------------------------|
| Wins              | `CHALLENGE_WINS`              | The amount of challenges the users has won.              | When the user wins a challenge.                             |
| Losses            | `CHALLENGE_LOSSES`            | The amount of challenges the user has lost.              | When the user loses a challenge.                            |
| Winstreak         | `CHALLENGE_WINSTREAK`         | The amount of wins the user has gotten in a row.         | When the user wins a challenge, resets to 0 when they lose. |
| Longest Winstreak | `CHALLENGE_LONGEST_WINSTREAK` | The largest amount of wins the user has gotten in a row. | When they get a new longest winstreak.                      |
| Bets Won          | `CHALLENGE_BETS_WON`          | The amount of bets the user has won.                     | When the user wins a bet.                                   |
| Bets Lost         | `CHALLENGE_BETS_LOST`         | The amount of bets the user has lost.                    | When the user loses a bet.                                  |

## Rewards
This game gives out the following rewards:
| Action                          | Reward                                             |
|---------------------------------|----------------------------------------------------|
| Winning the game                | +100xp, +50 Skuddbux, +1 win                       |
| Winning multiple games in a row | +50xp, +25 Skuddbux (multiplied by amount of wins) |
| New highest winstreak           | Longest challenge winstreak updated                |

## Betting system
Challenge features a betting system where you can bet Skuddbux on the user themself winning the fight. The bet amount is decided by the challenger and is agreed upon by the challenged. 

### Matching bets
In challenge both participating parties must bet the same amount. In the event that the challenger is betting more than the challenged person has, the bet of the challenger is automatically lowered to the amount the challenged person has. This means this user has to go all-in to play.

### Accepting a bet
To accept a bet, the user simply accepts the fight, the bet will be paid and the game will start.

### Declining a bet
To decline the bet, the user declines the fight, and the bet of the challenger is automatically refunded to them.

### Payout
The winner of the fight will recieve double their bet, the loser of the fight gets nothing. There are stats that are being tracked based on winning or losing bets.

## Cooldown
This game has a 1 minute cooldown period, this applies to both users in the game and starts when the game ends. Users on cooldown may not start a new game, but they may still accept another.

## Commands
The command for challenge is `!challenge`.
This command also listens to the following aliases:  
* `!duel`
* `!fight`
* `!1v1`

#### Command parameters
| Parameter | Type            | Description                                                                                       | Required |
|-----------|-----------------|---------------------------------------------------------------------------------------------------|----------|
| Mention   | User Mention    | Defines which user needs to be challenged, accepts when there's a eligible challenge outstanding. | Yes      |
| Bet       | Number / String | Defines the bet the user wants to place.                                                          | No       |
| **OR**    |                 |                                                                                                   |          |
| Mention   | User Mention    | Defines which user needs to be challenged, accepts when there's a eligible challenge outstanding. | Yes      |
| Decline   | Keyword         | Defines if the user wants to decline a fight.                                                     | Yes      |
| **OR**    |                 |                                                                                                   |          |
| `open`    | Keyword         | When the open keyword is provided, a open challenge will be started.                              | Yes      |
| Bet       | Number / String | Defines the bet the user wants to place.                                                          | No       |
| **OR**    |                 |                                                                                                   |          |
| `cancel`  | Keyword         | When the cancel keyword is provided, the user's outstanding challenge will be cancelled.          | Yes      |
{% hint style="info" %}
Refer for to the [Betting Shortcuts](/Minigames/betting-shortcuts.md) articles, to see what shortcuts are currently available and what you can specify as your bet.
{% endhint %}

#### Command examples
| Example                                            | Action                                                                                                                                               | Response                                                      |
|----------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------|
| `!challenge @MyNameIsDave#0123`                    | User `MyNameIsDave#0123` will be challenged with the user's `DEFAULT_BET` value as the bet or when there's a eligible challenge it will be accepted. | A new challenge or a fight is started                         |
| `!challenge @MyNameIsDave#0123 100`                | User `MyNameIsDave#0123` will be challenged to a fight with 100 Skuddbux as the bet.                                                                 | A new challenge.                                              |
| `!challenge @MyNameIsDave#0123 <betting shortcut>` | User `MyNameIsDave#0123` will be challenged to a fight with the specified bet.                                                                       | A new challenge.                                              |
| `!challenge @MyNameIsDave#0123 0`                  | User `MyNameIsDave#0123` will be challenged to a fight with no bet.                                                                                  | A new challenge.                                              |
| `!challenge @MyNameIsDave#0123 decline`            | If there's a outstanding fight with user `MyNameIsDave#0123` it will be declined.                                                                    | ![](https://i.imgur.com/rEFJP65.png) reaction on the message. |
| `!challenge open`                                  | A new open challenge is started user's `DEFAULT_BET` value as the bet.                                                                               | A new open challenge.                                         |
| `!challenge open 100`                              | A new open challenge is started with 100 Skuddbux as the bet.                                                                                        | A new open challenge.                                         |
| `!challenge open <betting shortcut>`               | A new open challenge is started with the specified bet.                                                                                              | A new open challenge.                                         |
| `!challenge open 0`                                | A new open challenge is started with no bet.                                                                                                         | A new open challenge.                                         |
| `!challenge cancel`                                | If there's one, the outstanding challenge is canceled.                                                                                               | ![](https://i.imgur.com/rEFJP65.png) reaction on the message. |
{% hint style="info" %}
Reactions can be clicked to get a more detailed response.
{% endhint %}

#### Permission requirements
This command requires no permissions.
{% hint style="info" %}
For more information about permissions, view the [Permissions](/Systems/permissions.md) article.
{% endhint %} 