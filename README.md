![SerafallRobot]( https://telegra.ph/file/00abaa996277e1d439d0c.jpg )
# SerafallRobot 
<p align="center">

A modular Telegram Python bot running on python3 with a sqlalchemy database.

Originally a SaitamaRobot fork, SerafallRobot evolved further and was built to be more robust. 

* Bot link:  <a href="https://t.me/Serafall_Leviathan_bot" alt="SerafallRobot"> <img src="https://img.shields.io/badge/Bot__Link-SerafallRobot-green" /> </a>




## How to setup/deploy.

### Read these notes carefully before proceeding 
 - Your code must be open source and a link to your fork's repository must be there in the start reply of the bot
 - This repo does not come with technical support, so DO NOT come to us asking help about deploy/console errors
 
<details>
  <summary>Steps to self Host!! </summary>

  ## Setting up the bot (Read this before trying to use!):
Please make sure to use python3.6, as I cannot guarantee everything will work as expected on older Python versions!
This is because markdown parsing is done by iterating through a dict, which is ordered by default in 3.6.

  ### Python dependencies

Install the necessary Python dependencies by moving to the project directory and running:

`pip3 install -r requirements.txt`

This will install all the necessary python packages.

  ### Database

If you wish to use a database-dependent module (eg: locks, notes, userinfo, users, filters, welcomes),
you'll need to have a database installed on your system. I use Postgres, so I recommend using it for optimal compatibility.

In the case of Postgres, this is how you would set up a database on a Debian/ubuntu system. Other distributions may vary.

- install postgresql:

`sudo apt-get update && sudo apt-get install postgresql`

- change to the Postgres user:

`sudo su - postgres`

- create a new database user (change YOUR_USER appropriately):

`createuser -P -s -e YOUR_USER`

This will be followed by you need to input your password.

- create a new database table:

`createdb -O YOUR_USER YOUR_DB_NAME`

Change YOUR_USER and YOUR_DB_NAME appropriately.

- finally:

`psql YOUR_DB_NAME -h YOUR_HOST YOUR_USER`

This will allow you to connect to your database via your terminal.
By default, YOUR_HOST should be 0.0.0.0:5432.

You should now be able to build your database URI. This will be:

`sqldbtype://username:pw@hostname:port/db_name`

Replace sqldbtype with whichever DB you're using (eg Postgres, MySQL, SQLite, etc)
repeat for your username, password, hostname (localhost?), port (5432?), and DB name.

  ## Modules
   ### Setting load order.

The module load order can be changed via the `LOAD` and `NO_LOAD` configuration settings.
These should both represent lists.

If `LOAD` is an empty list, all modules in `modules/` will be selected for loading by default.

If `NO_LOAD` is not present or is an empty list, all modules selected for loading will be loaded.

If a module is in both `LOAD` and `NO_LOAD`, the module will not be loaded - `NO_LOAD` takes priority.

## Starting the bot.

Once you've set up your database and your configuration is complete, simply run (Linux):

`python3 -m SerafallRobot`

For queries or any issues regarding the bot please open an issue ticket or visit us at [AstrakoBotSupport](https://t.me/AstrakoBotSupport)


## Credits
The bot is based on the original work done by [PaulSonOfLars](https://github.com/PaulSonOfLars) and [AnimeKaizoku](https://github.com/AnimeKaizoku)
All original credits go to Paul and AnimeKaizoku, Without their efforts, this fork would not have been possible!

Any other authorship/credits can be seen through the commits.

Should any be missing kindly let us know at [AstrakoBotSupport](https://t.me/AstrakoBotSupport) or simply submit a pull request on the readme.
