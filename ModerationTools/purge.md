# Purge command

## Introduction
The purge feature allows server owners to mass delete messages using Skuddbot.

## Starting a purge
To start a purge a user types the command `!purge <amount>`. The bot will immediately start purging the amount of messages specified.

### Purging more than 500 messages
When the user specifies a number greater than 500 the bot will ask for a confirmation before the purge is started. The user can confirm the purge using the ![](https://i.imgur.com/rEFJP65.png) reaction, after which it is started. To cancel the purge, the user clicks the ![](https://i.imgur.com/n2UfbMz.png) reaction.

{% hint style="info" %}
For more information about the command, view the [command](#command) section.
{% endhint %}

## Time to complete a purge
Sometimes a purge might take longer than expected. This is to do with the way the Discord API works.

### Sending requests to the API
The bot can send roughly 10 requests every 10 seconds to the API. When the bot sends more than this, Discord will deny the requests.

### Purging messages younger than 2 weeks
When purging messages younger than 2 weeks, the bot can send bulk delete requests, of 100 messages per request. Given the bot can send 10 requests every 10 seconds, the bot can purge these messages with a rate of roughly 1000 messages/10 seconds.

### Purging messages older than 2 weeks
When purging messages older than 2 weeks, the bot can't use the bulk delete endpoint. In this instance the bot will need to delete every message one by one. Given the request limit in this instance is still 10, the bot can now only delete at a rate of 10 messages/10 seconds.

## Command
The command for purging messages is `!purge`.

#### Command parameters
| Parameter       | Type   | Description                                  | Required? |
|-----------------|--------|----------------------------------------------|-----------|
| Amount to purge | Number | Defines how much messages should be deleted. | Yes       |

#### Command examples
| Example      | Action                                                                                                                                                      | Response                     |
|--------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------|
| `!purge 100` | Purges the 100 most recent messages in the channel where it was used.                                                                                       | Purge in progress indicator. |
| `!purge 501` | Will queue a purge of the 501 most recent messages in the channel where it was used. The user will be asked for a confirmation before the purge is started. | Confirmation message.        |
#### Permission requirements
This command requires the `SERVER_ADMIN` permission
{% hint style="info" %}
For more information about permissions, view the [Permissions](/Systems/permissions.md) article.
{% endhint %}