# Free for All

## Introduction
Free for All is a minigame where multiple users can battle, but only one will emerge victorious!

## Game flow
### Starting a game
A game is started with the `!freeforall` command. The user starting the game will be the host of the game.
A new game will be created and is put into what is known as the "outstanding" phase. There can only be one outstanding game per server.
{% hint style="info" %}
The [command](#command) section contains more details about the command.
{% endhint %}

### Entering the game
When a game is outstanding, a user can enter the game in 2 ways, without a bounty or with a bounty. Entering without a bounty may be done by clicking the ![](https://i.imgur.com/o8SZQlF.png) reaction. When the user wants to enter with their default bet as the bounty they click the ![](https://i.imgur.com/rgDJ0uw.png) reaction. To match the highest current bounty, the user clicks the ![](https://i.imgur.com/LqZbyj6.png) reaction. When a user wants to bet a different amount they use the command: `!freeforall <bounty>`. 

{% hint style="info" %}
* Refer for to the [Betting Shortcuts](/Minigames/betting-shortcuts.md) articles, to see what shortcuts are currently available and what you can specify as your bounty.
* For more information about the bounty system, view the [Bounty system](#bounty-system) section.
{% endhint %}
{% hint style="danger" %}
When entering with your default bet or matching the current highest bounty, and your balance is not enough, you will go **all-in**.
{% endhint %}

### Leaving the game
#### Using reactions
A user can leave the game by removing either the ![](https://i.imgur.com/o8SZQlF.png), ![](https://i.imgur.com/rgDJ0uw.png) or ![](https://i.imgur.com/LqZbyj6.png) reaction.
It does not matter whether they placed a bounty or not. Removing any of those reactions will make the user leave the game.

#### Using commands
A user can leave the game by typing `!freeforall leave`, any placed bounty will be refunded.

### Changing bounty
If a user wants to change their bounty, they first must leave the game and then re-join it with their new bounty.

### Starting the fight
When a game is outstanding, the host of the game can start the fight by clicking the ![](https://i.imgur.com/rEFJP65.png) reaction. The Free for All must contain at least 3 entrants for it to be started. When the game is started, the results will be revealed after 5 seconds.

#### Force-starting the fight
Users with the server admin permission can force-start the fight, this is done by adding the ![](https://i.imgur.com/UUpPhCO.png) reaction to the message. When forcefully starting a Free for All the entrants requirement is lowered from 3 to 2.
The fight will be marked as started by admin.
{% hint style="info" %}
For more information about permissions, view the [Permissions](/Systems/permissions.md) article.
{% endhint %}

### Post-game
The fight of Free for All is simulated in the background, meaning users actually kill each other, from this the bot generates a kill feed. The kill feed can be viewed by clicking the ![](https://i.imgur.com/7fUiBDQ.png) reaction. To view the rewards breakdown, click the ![](https://i.imgur.com/BlfMxg2.png) reaction.  

A more verbose kill feed and rewards are available via a Game Log, press the ![](https://i.imgur.com/mFwHxkd.png) reaction to receive the download link.

{% hint style="info" %}
For more information about Game Logs, view the [Game Logs](/Minigames/Game-Logs.md) article.
{% endhint %}

## Stats
| Stat                 | Technical name          | Tracks                                                          | Awarded                                            |
|----------------------|-------------------------|-----------------------------------------------------------------|----------------------------------------------------|
| Wins                 | `FFA_WINS`              | The amount of times the user has won a Free for All             | When the user wins the Free for All                |
| Losses               | `FFA_LOSSES`            | The amount of times the user has been killed in a Free for All. | When the user gets killed in the Free for All      |
| Highest entrants win | `FFA_HIGHEST_WIN`       | The highest amount of entrants in a game the user has won.      | When the user achieves a new highest entrants win. |
| Kills                | `FFA_KILLS`             | The amount of kills the user has gotten in a Free for All.      | When the user kills someone in a Free for All      |
| Bounties survived    | `FFA_BOUNTIES_SURVIVED` | The amount of bounties the user has survived.                   | When the user survives a bounty.                   |
| Bounties lost        | `FFA_BOUNTIES_LOST`     | The amount of bounties the user has lost.                       | When the user loses a bounty.                      |
{% hint style="info" %}
* For more information about stats, view the [stats](/Features/stats.md) article.
* For more information about the betting system, view the [betting system](#betting-system) section.  
{% endhint %}

## Rewards
This game gives out the following rewards:
| Action                                       | Reward                           |
|----------------------------------------------|----------------------------------|
| Killing a user                               | +50xp, +10 Skuddbux, +1 FFA kill |
| Winning the game                             | +100xp, +50 Skuddbux, +1 FFA win |
| Winning the game with a new highest entrants | FFA highest entrants updated     |

## Bounty system
When a user enters a free for all they can place an optional bounty on their head. Others may collect this bounty by killing the user. The bounty also figures as a baseline for how much the user can collect from others, the more they place on their own head, the more they may collect from others.

### Maximum earnings

The bounty placed on the users head figures as a baseline for how much they can collect from other users. This number is 250% of their own bounty, if an user puts 100 Skuddbux on their own head, they may collect up to 250 Skuddbux per other player killed.

### Collecting bounties

Users may collect the bounties from other players, when the user kills another player, they take their full bounty, up to 250% of their own bounty. If there's any excess money, it stays with the victim.

### Stealing bounties

Collected bounties can be stolen, if a user gets killed by another player. They will lose half of their collected bounties, this amount goes to the killer, the other half they get to keep and will be paid out upon game end. The 250% cap does not apply to stealing bounties.

### Surviving the bounty

When the user wins the game, they will receive their own bounty double in addition to any other funds they collected during the game.

### Filling up the jackpot

Any funds that remain unclaimed after the game has ended, will get split in half. One half goes back to the user that placed that bounty on their own head, and the other half will contribute towards the jackpot.

{% hint style="info" %}
* For information on how to place bounties, view the [entering the game](#entering-the-game) section.  
* For more information on stats, view the [stats](#stats) section.  
* For more information about the jackpot, view the [jackpot](/Systems/jackpot.md) article.  
{% endhint %}

## Reminders and Auto-starting
Every 6 hours the host will be reminded of a outstanding game via a DM, but only if the following conditions are met:
* The game has atleast 3 entrants,.
* The host has their minigames reminders enabled.

The game will auto-start if:
* The entrants, since the last reminder, haven't increased.
* The game has been outstanding for at least 12 hours.

When the fight is auto-started, the fight is marked as auto-started by bot.
{% hint style="info" %}
For more information about enabling [minigame reminders](/Features/user-settings.md#minigame-reminders), view the [user settings](/Features/user-settings.md) article.
{% endhint %}

## Cooldown
This game has a 5 minute cooldown period, this applies to all entrants of the game and starts when the game ends. Users on cooldown may not start a game, but they may still enter it.

## Commands
The command for Free for All is `!freeforall`.
This command also listens to the following alias: `!ffa`.

#### Command parameters
| Parameter | Type   | Description                                                      | Required? |
| --------- | ------ | ---------------------------------------------------------------- | --------- |
| Bounty    | Number | Defines the bounty the user wants to place.                      | No        |
| **OR**    |        |                                                                  |           |
| `leave`  | Keyword | When the leave keyword is provided the user will leave the game. | Yes       |

{% hint style="info" %}
Refer for to the [Betting Shortcuts](/Minigames/betting-shortcuts.md) articles, to see what shortcuts are currently available and what you can specify as your bounty.
{% endhint %}


#### Command examples
| Example                          | Action                                                       | Response                                                  |
| -------------------------------- | ------------------------------------------------------------ | --------------------------------------------------------- |
| `!freeforall`                    | The user will be entered into the game with their default bet as their bounty. | The message is deleted and the game message updated.      |
| `!freeforall 0`                  | The user will be entered into the game with no bounty.       | The message is deleted and the game message updated.      |
| `!freeforall 100`                | The user will be entered into the game with 100 Skuddbux as their bounty. | The message is deleted and the game message updated.      |
| `!freeforall <betting shortcut>` | The user will be entered into the game with the specified bet as their bounty. | The message is deleted and the game message updated.      |
| `!freeforall leave`              | The user leaves the game.                                    | Confirmation of game leaving and game message is updated. |
{% hint style="info" %}
* When there's no current game active, using a command to enter the game will automatically create a new game.
* Reactions can be clicked to get a more detailed response.
{% endhint %}

#### Permission requirements
This command requires no permissions.
{% hint style="info" %}
For more information about permissions, view the [Permissions](/Systems/permissions.md) article.
{% endhint %}
