<p align="center"><img src="https://raw.githubusercontent.com/Blackstonecoden/Global-Chat/main/LOGO.png" alt="Global Chat Logo" width="200"></p>
<h1 align="center">Global Chat - Python<br>
	<a href="https://github.com/Blackstonecoden/Global-Chat-Python"><img src="https://img.shields.io/github/stars/blackstonecoden/Global-Chat-Python
    "></a>
	<a href="https://discord.gg/FVQxgBysA7"><img src="https://img.shields.io/discord/1201557790758551574?color=5865f2&label=Discord&style=flat" alt="Discord"></a>
	<br><br>
</h1>

---

## What is the Global Chat BOT?

The Global Chat BOT is a small hobby of mine, where I took a simple base and improved upon it. The original base code is from [CoasterFreak](https://www.youtube.com/watch?v=Ri8RP5AVAFc&list=PLSgiAkLaBUJ8hZUaDs1AcEQ-e1oSBChy1&index=9). IMPORTANT: The code may not necessarily be the best, but it should suffice for a smaller Global Chat for up to 200 servers.

If you'd like to test the features of the Global Chat BOT, feel free to invite the original BOT: [Invite](https://discord.com/oauth2/authorize?client_id=1177590897152622672&permissions=1101659499601&scope=bot%20applications.commands)

---

# Setup

If you want to create your own Global Chat BOT, follow these steps. I will demonstrate the installation using the Pterodactyl software.

### Requirements:

- A server capable of hosting the BOT (Python required)
- A MySQL / MariaDB server

## 1. Download

Click on 'Code' at the top, download as ZIP. On your server panel, create a new server and upload the ZIP file into the root directory. Extract it, and delete the ZIP file. In the directory, there should now be 4 files: `.env.example`, `README.md`, `.gitignore`, `LICENSE.md`, and a folder named `src`. You can delete all files except .env.example and the src folder.

## 2. Setup the config files and libraries

### 2.1 Setup of the .env file

First, we will edit the .env file. Open the .env.example file and fill in all the information. The comments can assist you. Ensure you input the token, database username, and password, etc., without quotation marks. Once you've filled everything in, rename the file to `.env`. The file should look something like this:

```.env
TOKEN = ijasodk1239i821
config_file = ./src/config.json

database_host = 192.168.178.11
database_port =  3306
database_user = admin
database_passwd = pasword1234
database_database = globalchat
```

### 2.2 Setup of the config.json file

Next, the config.json will be edited. To do this, open the file `./src/config.json.example` and fill in all the information. IMPORTANT: Since it is a JSON file, you need to remove the comments, which means everything following a #. The tables named database, message_database, etc., are specified in the setup.py file. The fields icon_announcement and icon_important are not needed. Now rename the file to `config.json`. Here is an example of a config.json:

```json
{
  "swear_file_path": "./src/swear.txt",
  "bot_settings_file_path": "./src/bot_settings.json",
  "emoji_file_path": "./src/emoji.txt",
  "color_file_path": "./src/color.json",

  "database": "server_list",
  "message_database": "message_ids",
  "user_data_databse": "user_data",
  "ban_database": "ban_list",

  "bot_name": "Global Chat",
  "bot_status": "Is Global",
  "bot_logo_url": "https://raw.githubusercontent.com/Blackstonecoden/Global-Chat/main/LOGO.png",

  "admin_guild": 1821182535732195922,
  "channel_admin_log": 1226092732317868944,
  "channel_staff_log": 1921092252608670088,
  "channel_report_log": 12067942277033260245,

  "bot_invite": "https://discord.com/api/oauth2/authorize?client_id=1177590897152622672&permissions=1101659499601&scope=bot%20applications.commands",
  "bot_support_server": "https://discord.gg/FVQxgBysA7",
  "bot_website": "https://www.discord.com",

  "standard_server_icon": "hhttps://raw.githubusercontent.com/Blackstonecoden/Global-Chat/main/BLANK_ICON.jpg",
  "icon_announcement": "",
  "icon_important": ""
}
```

### 2.3 Installing all needed libraries

Finally, you need to install all the required libraries. If you have a Pterodactyl server, click on `Server > Startup > Additional Python Packages`, and add the following there: `discord.py pytz colorama`

If you have a different server, you need to enter `pip install <library>` for each library in the console.

## 3. Final setup

### 3.1 Database setup

The last thing that needs to be set up now is the database. Navigate to `./src/setup.py` and edit the `admin_user` variable. This user will have admin privileges and can change the roles and permission level of other users on Discord using /set-role. Execute the file. After that, it will no longer be needed. However, you can keep it in case you lose access to the BOT and need to set a new admin user.

### 3.2 BOT startup

Now you can start the BOT. Make sure you have completed all the preceding steps. If you're using Pterodactyl, go to your `Server > Startup > Bot Py File` and add `./src/bot.py` there. The BOT should now start without any errors. If there are any issues, feel free to join our [Discord](https://discord.gg/FVQxgBysA7) server and request assistance there.
