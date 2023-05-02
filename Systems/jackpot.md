# Jackpot

## Introduction
The Jackpot is a system that allows a jackpot to continously build up over time and that users can win to claim the amount that is in the jackpot at that time.

## Filling the jackpot
### Voiding Skuddbux
Any user can fill up the jackpot by voiding Skuddbux in minigames. Any voided Skuddbux will get added to the jackpot.

### Editing the jackpot
Users with the `SERVER_ADMIN` permission may edit the jackpot using the `!serversettings` command.
{% hint style="success" %}
Under normal circumstances there's no need for server admins to edit the Jackpot.
{% endhint %}
{% hint style="info" %}
* For more information about permissions, view the [Permissions](/Systems/permissions.md) article.
* For more information about the Server settings command, view the [Server settings](/Features/server-settings.md) article.
{% endhint %}

## What are voided Skuddbux?
Voided Skuddbux are Skuddbux that are betted by users in minigames but not paid out. For example: A free for all with 3 entrants has 2 users betting and one doesn't, and the user that didn't bet wins. In this instance the bets from the other two users won't be paid out and will be added to the jackpot instead.

Skuddbux can be voided in the following Minigames:
* [Blackjack](/Minigames/blackjack.md)
* [Free for All](/Minigames/free-for-all.md)
* [Double or Nothing](/Minigames/double-or-nothing.md)

## Viewing the jackpot
### Jackpot command
Everyone can view the current jackpot amount using the `!jackpot` command.
{% hint style="info" %}
For more information about the command, view the [command](#command) section.
{% endhint %}

### Server settings command
People with the `SERVER_ADMIN` permission can also use the `!serversettings` command to view the current jackpot.
{% hint style="info" %}
* For more information about permissions, view the [Permissions](/Systems/permissions.md) article.
* For more information about the Server settings command, view the [Server settings](/Features/server-settings.md) article.
{% endhint %}

## Winning the jackpot
{% hint style="warning" %}
This feature is still under development.
{% endhint %}

## Command
The command for viewing the Jackpot is: `!jackpot`.

#### Command parameters
This command requires no parameters.

#### Command examples
| Example    | Action                            | Response                                   |
|------------|-----------------------------------|--------------------------------------------|
| `!jackpot` | Shows the current jackpot amount. | A message with the current jackpot amount. |

#### Permission requirements
This command requires no permissions.
{% hint style="info" %}
For more information about permissions, view the [Permissions](/Systems/permissions.md) article.
{% endhint %}