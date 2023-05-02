# Game Logs 

## Introduction
Game Logs is a feature that generates text files with the history of what happens in minigames. These text files can be downloaded and opened to see what happened. They typically contain more verbose logging than what is visible in Discord. - They are not meant to be a replacement, but an addition to what is visible in Discord.

## Supported minigames
Currently the following minigames have support for game logs:
* [Free for All](/Minigames/free-for-all.md)

## Obtaining a Game Log
Game logs are available through reactions, when a Game Log is avaiable, the bot will add a reaction to the message (the emoji may vary), which will present the user with a download link once the reaction has been clicked. Just like any other reaction, it will expire after a set amount of time (this time may vary).

## Anonymized usernames
Users can choose to let their names be anonymized. Game Logs do not show full Discord usernames and discriminators combinatons, but just nicknames. But when a user does not have a nickname set, their full username will still be shown, just without the discriminator.
Users can turn this setting on by setting the User setting `ANON_GAME_LOG` to `true`.
{% hint style="info" %}
For more information about User Settings, view the [User Settings](/Features/user-settings.md) article.
{% endhint %}

### Identifying anonymized users
Users that have chosen to anonymize their username, will be shown as `AnAnonymousUser01`, `AnAnonymousUser02`, etc. This way anonymous users can still be identified as entities, but not be traced back to a Discord user, unless the reader of the log has access to the Discord the game has happened in.