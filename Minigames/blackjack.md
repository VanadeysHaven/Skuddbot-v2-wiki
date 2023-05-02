# Blackjack

## Introduction
In this minigame a user can play a game of Blackjack against a dealer.

## Game rules
* The goal of Blackjack is getting your hand value as close as possible to 21 without going over 21, and beating the dealer.
* The cards 2 through 10 have the value of their rank. A jack, queen and king are each worth 10. And a ace is worth 11, unless it busts you, then it's worth 1.
* The game is played with a 8 standard decks of 52 playing cards.
* Blackjack is achieved by having a hand value of 21; a ace and either a 10, king, queen or jack.
* Dealer draws to 16, stands on 17. - Dealer also stands on soft 17.
* Winning pays 1 to 1, Blackjack pays 3 to 2, Push pays equal.

## Game interface
### Card reprensentation
The cards are represented by two emoji's. For example;  ![](https://i.imgur.com/30ClJ6w.png) ![](https://i.imgur.com/JW2EzbC.png) represents a club 4, and ![](https://i.imgur.com/xTgf808.png) ![](https://i.imgur.com/FQZwXq7.png) represents a hearts ace.  

### Normal hand
![](https://i.imgur.com/d9n2qkf.png)  
**1.** Nickname of the user playing this game.  
**2.** Hand value of the dealer  
**3.** Cards in dealer hand. - Hole card is represented by two ![](https://i.imgur.com/RF1kUpc.png) emoji's.  
**4.** Hand value of the player.  
**5.** Bet of the player.  
**6.** Cards in player hand.  
**7.** Playing instructions. - This section also shows the current state of the game.  
**8.** Reactions. The user clicks these to make their move.  

### Split hand
![](https://i.imgur.com/Lxojyvk.png)  
**1.** Nickname of the user playing this game.  
**2.** Hand value of the dealer  
**3.** Dealer cards. - Hole card is represented by two ![](https://i.imgur.com/RF1kUpc.png) emoji's.  
**4.** Hand values of the player. - First number represents the first hand, second number the second hand.  
**5.** Bets of the player. - First number represents the first hand, second number the second hand.  
**6.** Current hand indicator. - This arrow points at the hand the user is currently playing.  
**7.** Player cards.  
**8.** Playing instructions. - This section also shows the current state of the game.  
**9.** Reactions. The user clicks these to make their move.

## Game flow
### Starting a game
To start a game the users types the command `!blackjack` optionally a user can specify a bet, when the user doesn't it will default to their `DEFAULT_BET` setting.

#### Getting Blackjack
When you get Blackjack, the game immediately ends and you win.

{% hint style="info" %}
* For more information about the [default bet](/Features/user-settings.md#default-bet), view the [user settings](/Features/user-settings.md) article.
* For more information about the command, view the [commands](#commands) section.
{% endhint %}

### Making moves
The user can choose from 4 different moves; hit, stand, double down or split. Not all moves are available all the time.

#### Hitting
The user can hit by clicking the ![](https://i.imgur.com/WGRpT3z.png) reaction. When the user hits, the dealer will deal another card to the user. The user can keep hitting until they get 21, when they will automatically stand, or when they bust, then they will lose.

#### Standing
The user can stand by clicking the ![](https://i.imgur.com/eACscH6.png) reaction. When the user stands, the user will not get another card and the dealer starts playing. If the user has two hands by splitting on the first turn, and they are on the first hand when standing, they continue playing with the second hand.

#### Doubling down
The user can double down by clicking the ![](https://i.imgur.com/oE4pdbJ.png) reaction. When the user double's down, they will double their bet and recieve one more card, after which they are forced to stand. 
{% hint style="info" %}
A user can only double down when: 
* Their hand value is 10 or less.
* When the hand contains exactly 2 cards.
{% endhint %}

#### Splitting
The user can split by clicking the ![](https://i.imgur.com/oFRcWTJ.png) reaction. When the user splits, their two cards are divided into two hands and they will recieve another card in each hand and their bet is doubled. After which they can continue playing as normal. The current hand being played is indicated by the ![](https://i.imgur.com/3pFjjWm.png) emoji.
{% hint style="info" %}
A user can only split when:
* When they have only one hand.
* They have exactly two  cards.
* The rank of the two cards are the same **OR** they are both face cards.
{% endhint %}

## Stats
| Stat                | Technical Name   | Tracks                                                             | Awarded                                                  |
|---------------------|------------------|--------------------------------------------------------------------|----------------------------------------------------------|
| Wins                | `BJ_WINS`        | The amount of hands the user has won in Blackjack .                | When the user wins a hand in Blackjack.                  |
| Losses              | `BJ_LOSSES`      | The amount of hands the user has lost in Blackjack.                | When the user loses a hand in Blackjack.                 |
| Pushses             | `BJ_PUSHES`      | The amount of hands the user has pushed in Blackjack.              | When the user ties a hand in Blackjack.                  |
| 21's                | `BJ_TWENTY_ONES` | The amount of 21's the user has gotten in Blackjack.               | When the user has a hand with the value 21 in Blackjack. |
| Blackjack's         | `BJ_BLACKJACKS`  | The amount of blackjacks the user has gotten.                      | When the user has Blackjack in Blackjack.                |
| Double Down Wins    | `BJ_DD_WINS`     | The amount of doubled down hands the user has won in Blackjack.    | When the user has won a doubled down hand in Blackjack.  |
| Double Down Pushes  | `BJ_DD_PUSHES`   | The amount of doubled down hands the user has pushed in Blackjack. | When the user pushes a doubled down hand in Blackjack.   |
| Doubled Down Losses | `BJ_DD_LOSSES`   | The amount of doubled down hands the user has lost in Blackjack.   | When the user has lost a doubled down hand in Blackjack. |

## Rewards
| Action                       | Reward                                                    |
|------------------------------|-----------------------------------------------------------|
| Getting Blackjack            | +350xp, +1 Blackjack, +1 21, +1 win, bet pays 3 to 2      |
| Winning with 21              | +225xp, +1 21, +1 win, bet pays 1 to 1                    |
| Winning from the dealer      | +150xp, +1 win, bet pays 1 to 1                           |
| Tied with the dealer with 21 | +100xp, +1 push, +1 21, bet pays equal                    |
| Tied with the dealer         | +50xp, + 1 push, bet pays equal                           |
| Winning a doubled down hand  | Double XP, +1 double down win, bet payout follows outcome |
{% hint style="info" %}
These rewards are awarded per hand. If a user wins both hands, you they get 2 wins.
{% endhint %}

## Jackpot
When the user loses, their bets will be added to the jackpot.
{% hint style="info" %}
For more information about the jackpot, view the [jackpot](/Systems/jackpot.md) article.
{% endhint %}

## Cooldown
This game has a 1 minute cooldown period, starting when the game ends.

## Gender neutral playing cards
Skuddbot has support for Gender neutral playing cards. Users can switch between the gender neutral playing cards and normal playing cards at any time they wish using the `GN_PLAYING_CARDS` user setting. When this setting is set to `true`, the ranks, jack, queen and king are replaced by bronze, silver and gold.
{% hint style="info" %}
For more information about User Settings, view the [User Settings](/Features/user-settings.md) article.
{% endhint %}

## Command
The command for Blackjack is `!blackjack`.  
This command also listens to the following aliases:
* `!bj`
* `!21`
* `!deal`

#### Command parameters
| Parameter | Type            | Description                                   | Required                             |
|-----------|-----------------|-----------------------------------------------|--------------------------------------|
| Bet       | Number / String | Defines the bet that the user wants to place. | ![](https://i.imgur.com/n2UfbMz.png) |
{% hint style="info" %}
Refer for to the [Betting Shortcuts](/Minigames/betting-shortcuts.md) articles, to see what shortcuts are currently available and what you can specify as your bet.
{% endhint %}

#### Command examples
| Example                         | Action                                                                           | Response                 |
|---------------------------------|----------------------------------------------------------------------------------|--------------------------|
| `!blackjack`                    | Starts a new game of Blackjack with the user's `DEFAULT_BET` setting as the bet. | A new game of Blackjack. |
| `!blackjack 100`                | Starts a new game of Blackjack with 100 Skuddbux as the bet.                     | A new game of Blackjack. |
| `!blackjack <betting shortcut>` | Starts a new game of Blackjack with the specified bet.                           | A new game of Blackjack. |
{% hint style="info" %}
For more information about the [default bet](/Features/user-settings.md#default-bet), view the [user settings](/Features/user-settings.md) article.
{% endhint %}

#### Permission requirements
This command requires no permissions.
{% hint style="info" %}
For more information about permissions, view the [Permissions](/Systems/permissions.md) article.
{% endhint %}
