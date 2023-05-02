# Message Database

## Introduction
The message database is a feature where donators can add strings of text to a list of messages. These messages are used throughout the bot mostly in a random fashion. 

## Message types
There are currently 8 types of messages:
| Name                     | Technical Name      | Description                                                                            | Maximum Length | Type         |
|--------------------------|---------------------|----------------------------------------------------------------------------------------|----------------|--------------|
| AI Name                  | `AI_NAME`           | Used for names of AI players in minigames.                                             | 64             | Text         |
| Bat Image                | `BAT`               | Used for URL's of images related to bats.                                              | 512            | URL or image |
| Bunny Image              | `BUNNY`             | Used for URL's of images related to bunnies.                                           | 512            | URL or image |
| Cake Image               | `CAKE`              | Used for URL's of images related to cakes.                                             | 512            | URL or image |
| Guinea Pig Image         | `GUINEA_PIG`        | Used for URL's of images related to guinea pigs.                                       | 512            | URL or image |
| Kitty Image              | `KITTY`             | Used for URL's of images related to cats.                                              | 512            | URL or image |
| Otter Image              | `OTTER`             | Used for URL's of images related to otters.                                            | 512            | URL or image |
| Owl Image                | `OWL`               | Used for URL's of images related to owls.                                              | 512            | URL or image |
| Panda Image              | `PANDA`             | Used for URL's of images related to panda's.                                           | 512            | URL or image |
| Playing Status           | `PLAYING`           | Used for text displayed in the playing status of Skuddbot.                             | 128            | Text         |
| Playing Status Christmas | `PLAYING_CHRISTMAS` | Used for text displayed in the playing status of Skuddbot during the Christmas period. | 128            | Text         |
| Playing Status New Year  | `PLAYING_NEW_YEAR`  | Used for text displayed in the playing status of Skuddbot during the New Years day.    | 128            | Text         |
| Puppy Image              | `PUPPY`             | Used for URL's of images related to dogs.                                              | 512            | URL or image |
| Seal Image               | `SEAL`              | Used for URL's of images related to seals.                                             | 512            | URL or image |
| Snake Image              | `SNAKE`             | Used for URL's of images related to snakes.                                            | 512            | URL or image |

## Command
{% hint style="warning" %}
Messages can currently only be added. Once you add them you cannot remove it. If you still wish to remove a message you added, please [contact](/Help/contact.md) me.
{% endhint %}

The command for adding messages is `!message`. This command is only available in DM's.

#### Command parameters
| Parameter | Type           | Description                                                                           | Required |
|-----------|----------------|---------------------------------------------------------------------------------------|----------|
| Operation | Keyword        | Can currently only be `add`.                                                          | Yes      |
| Type      | Technical Name | Technical name of the type that the user wants to add.                                | Yes      |
| Content   | String         | The content that the user wants to add. - Can also be images attached to the message. | Yes      |

#### Command examples
| Example                                    | Action                                                      | Response                                                      |
|--------------------------------------------|-------------------------------------------------------------|---------------------------------------------------------------|
| `!message add AI_NAME Dave`                | Adds the message "Dave" as a `AI_NAME` type.                | ![](https://i.imgur.com/rEFJP65.png) reaction to the message. |
| `!message add PUPPY example.com/image.png` | Adds the message "example.com/image.png" as a `PUPPY` type. | ![](https://i.imgur.com/rEFJP65.png) reaction to the message. |
| `!message add PUPPY <attached images>`     | Adds the URL's of the attached images as a `PUPPY` type.    | ![](https://i.imgur.com/rEFJP65.png) reaction to the message. |

#### Permission requirements
This command requires the `DONATOR` permission.
{% hint style="warning" %}
For more information about permissions, view the [Permissions](/Systems/permissions.md) article.
{% endhint %}
