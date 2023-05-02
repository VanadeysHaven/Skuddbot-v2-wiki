# Daily bonus

## Introduction
Users can claim a bonus of experience and currency each day. Bonuses scale exponentially if an user can upkeep their streak for claiming their bonus every day.

## Claiming a bonus
To claim a bonus, a user simply runs the command `!dailybonus`.
This command also listens to he following aliases:
* `!claim`
* `!db`

## Multiplier & Streak
Whitin the Daily Bonus system there are 2 main counters, a multiplier, and a streak. Both counters increase and decrease at the same rate. But the multiplier has a cap, and the streak does not. Meaning the mulitplier will stop increasing at a certain amount.

## Building a Multiplier & Streak
To build a multiplier and a streak a user must claim their bonus on consecutive days. Each consecutive day will increase the multiplier (given it's not a the cap) and streak by 1.

### Missing a day
When a user misses a day, a penalty will be incurred. The user's multiplier and streak will be decreased by 5 for every day missed. Additionally, the amount of missed days is added to a 'pause' counter. Which means the user's streak and multiplier will be frozen until this counter is back at 0.

#### Being frozen
When an user's freeze counter is above 0. The users streak and multiplier is frozen. This has the following effects;
* The user's multiplier and streak will not increase.
* The user's multiplier will not be applied to the bonusses, meaning they will only gain the base amount.

Every day the user claims their bonus, the pause counter will be decreased by one.
{% hint style="success" %}
If you only miss one day, your streak will only be frozen for that day. Meaning that the next time you claim, given it's on consecutive days, your multiplier will be applied again and your streak and multiplier will increase again.
{% endhint %}


## Bonus amount
### Bonus scaling
The bonuses scale exponentially. If a user can build up a streak of claiming their bonus every day, they will also increase their multiplier and gain more rewards over time.
There is a system to cap the multiplier at a certain day. When the cap is reached, a user can still claim their bonus every day, but the amount won't grow anymore. The user is however still allowed to grow their streak, and this is also recorded in the stats.

The bonus amount is calculated using the following formula:  
![](https://i.imgur.com/SNI3GS8.png)

### Controlling bonus amounts
Server admins can control the amounts of bonuses their users can claim every day. The following things can be customized with the `!serversettings` command:
* Currency base amount
* Experience base amount
* Bonus modifier
* Bonus multiplier cap
{% hint style="info" %}
For more information about [controlling bonus amounts](/Features/server-settings.md#daily-bonus), view the [Server settings](/Features/server-settings.md) article.
{% endhint %}

### Weekly bonus
Every 7 days the user isn't 'frozen', they will be eligable for a weekly bonus. This means their pay out for that day will be double. This does not apply to any seasonal bonusses.

## Cutoff point and offset
You can claim your bonus once per day. By default, a day is from midnight UTC until 23:59:59 UTC. This means the cutoff is, by default, at midnight UTC.

### Offset
A user can offset their cutoff point by 12 hours in either direction (-12 and +12). This is done using the `TIMEZONE` user setting.
{% hint style="success" %}
To figure out what your offset is, you can use the list of timezones on [timeanddate.com](https://www.timeanddate.com/time/zones/). Find your timezone in the table and see your offset in the right-most colum.
{% endhint %}
{% hint style="warning" %}
* Half hour offsets are not supported.
* When setting your offset using the `!usersettings` command, enter negative numbers as `-12` and positive numbers as `12` (no plus sign).
{% endhint %}
{% hint style="info" %}
For more information about user settings, view the [User settings](/Features/user-settings.md) article.
{% endhint %}

## Building a streak and multiplier
### Continuing and building a streak
To upkeep a streak, a user must claim their bonus on consecutive days, before the cutoff point.

### Losing a streak
Users can lose their streak when they do not claim their streaks on consecutive day. A penalty of 5 days is incurred for every day the user has missed. Every missed day is added to the pause counter.

### Viewing a streak
Streaks are recorded in the stats of a user, and can be viewed using the `!stats` command.
{% hint style="info" %}
For more information about stats, view the [stats](/Features/stats.md) article.
{% endhint %}
