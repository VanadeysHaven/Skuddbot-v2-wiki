# Double or Nothing

## Introduction
Double or Nothing is a minigame where users can bet their Skuddbux, and continuously double it or choose to bank the money. When a user chooses to double, there's a 50% chance it will double, if it doesn't double, the user looses everything.

## Game flow
### Starting a game
A game of Double or Nothing can be started using the command `!doubleornothing`.
{% hint style="info" %}
More detailed information about the command can be found in the [command](#command) section.
{% endhint %}

When a game is started a user is presented with the following message:  
![](https://i.imgur.com/7nU06AJ.png)
The user can now choose to double up or to take the money, using the reactions.

### Doubling up
A user can choose to double up by clicking the ![](https://i.imgur.com/oE4pdbJ.png) reaction.
When the user chooses to double up, there's a 50% chance of either of two outcomes:

#### Double
The bet gets doubled and the user is presented with the choice do double up again, or to take the money.

#### Nothing
The user loses everything, and the game ends.

### Taking the money
A user can choose to take the money by clicking the ![](https://i.imgur.com/LqZbyj6.png) reaction.
When a user to chooses to take the money, the game will end and the standing amount will get added to the user's Skuddbux balance.
{% info style="warning" %}
When choosing to take the money without doubling up before, no stats will be awarded and the bet amount will be refunded.
{% endhint %}

## Stats
| Stat           | Technical name       | Tracks                                                                                                    | Awarded                                                                |
|----------------|----------------------|-----------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------|
| Wins           | `DON_WINS`           | The amount of times the user has managed to take the money without loosing everything.                    | When the user chooses to take the money.                               |
| Losses         | `DON_LOSSES`         | The amount of times the user has chosen to double up, but lost everything.                                | When the user loses everything.                                        |
| Longest Streak | `DON_LONGEST_STREAK` | The maximum amount of times the user has managed to double up wihtin one game without loosing everything. | When the user has a new highest amount of double up's within one game. |
{% hint style="info" %}
For more information about stats, view the [stats](/Features/stats.md) article.
{% endhint %}

## Rewards
When the user rolls nothing, no rewards will be awarded.
When the user chooses to take the money, they will gain the amount of money they racked up, and a experience reward of 50xp for every double up they managed to get successfully.

## Jackpot
When the user rolls nothing, their initial bet will be added to the Jackpot.
{% hint style="info" %}
For more information about the jackpot, view the [jackpot](/Systems/jackpot.md) article.
{% endhint %}

## Command
The command for Double or Nothing is `!doubleornothing`.  
This command also listens to the following alias:
- `!don`

#### Command parameter
| Parameter | Type            | Description                                   | Required                             |
|-----------|-----------------|-----------------------------------------------|--------------------------------------|
| Bet       | Number / String | Defines the bet that the user wants to place. | ![](https://i.imgur.com/n2UfbMz.png) |
{% hint style="info" %}
Refer for to the [Betting Shortcuts](/Minigames/betting-shortcuts.md) articles, to see what shortcuts are currently available and what you can specify as your bet.
{% endhint %}

#### Command examples
| Example                               | Action                                                                  | Response                         |
|---------------------------------------|-------------------------------------------------------------------------|----------------------------------|
| `!doubleornothing`                    | Starts a new game of Double or Nothing with the default bet as the bet. | A new game of Double or Nothing. |
| `!doubleornothing 100`                | Starts a new game of Double or Nothing with the bet set to 100.         | A new game of Double or Nothing. |
| `!doubleornothing <betting shortcut>` | Starts a new game of Double or Nothing with the specified bet.          | A new game of Double or Nothing. |

#### Permission requirements
This command requires no permissions.
{% hint style="info" %}
For more information about permissions, view the [Permissions](/Systems/permissions.md) article.
{% endhint %}