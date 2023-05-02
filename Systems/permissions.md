# Permissions

## Introduction
Skuddbot features a simple permission system. This is used for checking what user is allowed to do what.

## Permissions list
| Permission   | Technical Name | Granted to                                                                                    | Global Permission? |
|--------------|----------------|-----------------------------------------------------------------------------------------------|--------------------|
| Default      | `DEFAULT`      | Everyone.                                                                                     | Yes                |
| Server admin | `SERVER_ADMIN` | The owner of a server and users that have the admin role as specified in the server settings. | No                 |
| Donator      | `DONATOR`      | Users that have been added to the donator list.                                               | Yes                |
| Bot admin    | `BOT_ADMIN`    | Users that have been added to bot admin list.                                                 | Yes                |
| Timmy        | `TIMMY`        | Only to user Vanadey's Haven#0001.                                                               | Yes                |
{% hint style="info" %}
* For more information about the [admin role setting](/Features/server-settings.md#granting-admin-permissions), view the [Server Settings](/Features/server-settings.md) article.  
* For more information about what these permissions grant access to, please refer to the respective article of what you are trying to access.
{% endhint %}

## Global permissions and Local permissions
Global permissions are the same for a user across all servers and DM's.
A local permission is assigned to a user on a per-server basis, this means a user might have a local permission in one server, but might not have it in a different server.

## Viewing permissions
A user can view their permissions at any time using the [User info command](/Commands/user-info-command.md). 