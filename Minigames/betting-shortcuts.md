# Betting shortcuts
 
## Introduction
Skuddbot features various shortcuts for betting, these consist of certain keywords and numbers with suffixes.
 
## Applicable Minigames
Currently the following minigames support these betting shortcuts:
- [Blackjack](/Minigames/blackjack.md)
- [Challenge](/Minigames/challenge.md)
- [Double or Nothing](/Minigames/double-or-nothing.md)
- [Free for All](/Minigames/free-for-all.md)

## Global Shortcuts
### Number
An user may specify an number as a bet, this will then become their bet.

### Default Bet
Specifying `bet` or nothing, will make the bet  be what the user's `DFAUALT_BET` user setting is set to.
{% hint style="info" %}
For more information about the [default bet](/Features/user-settings.md#default-bet), view the [user settings](/Features/user-settings.md) article.
{% endhint %}

###  All-in
Specifying `all`, will make the bet be what the user's Skuddbux balance is. Causing the user to go all-in.

### Half
Specifying `half`, will make the bet be half of what the user's Skuddbux balance is.

### Percentages
Specifying a percentage, will make the bet be what that percentage amount of the user's Skuddbux balance is.
Example: The user has 150 000 Skuddbux, and specifies `15%` as their bet. Then their bet will be 15 000. 

### Thousands
Users can also specify a bet in thousands, then their bet will be that what they specify.
Example: The user specifies `10k` as their bet, then the bet will be 10 000. Decimal points are also supported, meaning `1.5k` will translate to 1 500.


## Game specific shortcuts
### Free for All
#### Match
Specifying `match` will match the highest bet currently entered in the Free for All. When there are no users entred, the bet will be 0.
