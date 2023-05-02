# Running a self-hosted Skuddbot instance

{% hint style="warning" %}
Please be aware that running a self-hosted Skuddbot instance comes with **no warranty what-so-ever**! 
We take no responsibility for anything! If you manage to set your computer on fire, that's on you (but please send pictures, because that's impressive)!
{% endhint %}

## Prerequisites
This tutorial will assume the following;
- The user has a Discord account with 2FA enabled.
- The user has a basic understanding of how to work with a CLI, Git and Docker.
- The user has set up a machine running Ubuntu Server (20.04 LTS preferred), with;
    - A sudo enabled user called `skuddbot`.
    - A working internet connection.
    - SSH access.
    - [Docker Engine installed](https://docs.docker.com/engine/install/ubuntu/).
    - Git installed.


### Working directory
This tutorial will use `/opt/Skuddbot-v2` as it's working directory. The Git repo will reside inside this directory. Note that the working directory doesn't have to be placed in the `/opt` directory, it can be placed anywhere on the machine, but it must be named `Skuddbot-v2`.  

## Setting up a self-hosted instance
### Downloading Skuddbot
1. Connect to the server via SSH and log into the `skuddbot` user.
2. Navigate to `/opt`: `$ cd /opt`
3. Clone the Skuddbot-v2 repository: `$ sudo git clone https://github.com/VanadeysHaven/Skuddbot-v2.git`
4. Change ownership of the folder to the `skuddbot` user: `$ sudo chown -R skuddbot:skuddbot Skuddbot-v2`
5. Navigate into the folder: `$ cd Skuddbot-v2`  
  
![](https://i.imgur.com/xDYCJ0x.png)

### Creating a Discord bot user
1. Go to the [Discord Developer Portal](https://discord.com/developers/applications) (login required).
2. Create a new application, and name it `Skuddbot`.
3. Navigate to OAuth2, General and copy the Client ID, and save it for later use.
4. Go to Bot, and click Add Bot and confirm.
5. Reset the token, enter the 2FA code, copy the token and save it for later use.
6. Enable all 3 Privileged Gateway Intents, and save the changes.  

![](https://i.imgur.com/VGwb474.png)

### Inviting the bot to a server
1. Navigate to the [Discord Permissions Calculator](https://discordapi.com/permissions.html#8).
2. At the bottom paste the Client ID into the box that says Client ID.
3. Click the link at the bottom of the page, and follow the steps prompted on the screen to invite the bot to a server.

{% hint style="success" %}
This link can be shared with anyone to allow them to invite your self-hosted instance to their server.
{% endhint %}

### Configurating the bot
1. Connect to the server via SSH and log into the `skuddbot` user.
2. Navigate to `/opt/Skuddbot-v2/configs`: `$ cd /opt/Skuddbot-v2/configs`
3. Duplicate the `.env-example` file and name it `.env`: `$ cp .env-example .env`  
![](https://i.imgur.com/2EcLcu1.png)
4. Open the file using nano: `$ nano .env`
5. Paste in the Discord Token on the line that starts with `DISCORD_TOKEN`.
6. Change the `MYSQL_PASSWORD` and `MYSQL_ROOT_PASSWORD` to something strong.  
![](https://i.imgur.com/axeRd4m.png)
7. Press `CRTL+X` to close Nano, press `Y` and `ENTER` to confirm to save.
8. Navigate back to the parent folder: `$ cd ..`

### Starting the bot
1. Connect to the server via SSH and log into the `skuddbot` user.
2. Navigate to `/opt/Skuddbot-v2`: `$ cd /opt/Skuddbot-v2`
3. Run the update script: `$ bash update.sh --skip-db`

{% hint style="info" %}
**Please be patient on first startup.** First startup might take a while, please be patient while this process completes.  
The script will take care of configurating Skuddbot and will command the Docker Engine to install the bot on the machine. The required images will be downloaded as needed and the bot images will be built. When this process completes the bot will start up.
{% endhint %}
{% hint style="danger" %}
Stay connected to your machine while this process is running!
{% endhint %}

### Stopping the bot
1. Connect to the server via SSH and log into the `skuddbot` user.
2. Navigate to `/opt/Skuddbot-v2`: `$ cd /opt/Skuddbot-v2`
3. Run this command: `$ sudo docker compose down`
{% hint style="success" %}
When the bot is shut down, your database is safely stored in a volume, and will be automatically re-mounted into the database once you start the bot back up.
{% endhint %}

### Updating the bot
1. Connect to the server via SSH and log into the `skuddbot` user.
2. Navigate to `/opt/Skuddbot-v2`: `$ cd /opt/Skuddbot-v2`
3. Run the update script: `$ bash update.sh --skip-db`

{% hint style="info" %}
- The script will pull the latest version from GitHub, update the configurations and will command the Docker Engine to update the bot. The required images will be downloaded as needed and the bot images will be built. When this process completes the bot will start back up.  
- During this process a backup of your database is also taken. This backupis placed in the `backups` folder. Backups are named in this format: `backup-YYYYMMDDHHMMSS.sql`.
{% endhint %}
{% hint style="success" %}
You can skip backing up the database by adding the `--skip-db` flag to the command: `$ bash update.sh --skip-db`
{% endhint %}
{% hint style="danger" %}
Stay connected to your machine while this process is running!
{% endhint %}
The bot can be easily updated by running `$ bash update.sh`. This will pull the latest version from Github, update the configs, backup the database, rebuild the images and restart the bot.  
Backups of the database are placed in the `backups` folder. Backups are named in this format: `backup-YYYYMMDDHHMMSS.sql` Backing up the database can be skipped by adding the `--skip-db` flag to the command.

#### Updating to a different branch
To update to a different branch of the bot, use `$ git checkout` to switch to that branch, and then run `$ bash update.sh` as normal.

#### Importing a database backup
1. Connect to the server via SSH and log into the `skuddbot` user.
2. Navigate to `/opt/Skuddbot-v2`: `$ cd /opt/Skuddbot-v2`
3. List the contents of the `backups` folder: `$ ls backups` and choose the desired backup.
4. Copy the .sql file to `database/import_data` folder: `$ cp backup/backup-1234.sql database/import_data`
5. Shut the bot down: `$ sudo docker compose down`.
6. Remove the database volume, this is most likely called `skuddbot-v2_database`: `$ sudo docker volume rm skuddbot-v2_database`.
7. Start the bot: `$ bash update.sh --skip-db`

{% hint style="warning" %}
You may be required to create the `import_data` folder: `$ mkdir database/import_data`
{% endhint %}
{% hint style="danger" %}
Do not rename the backup.sql file. Leave it as is, otherwise it might not work.
{% endhint %}  
