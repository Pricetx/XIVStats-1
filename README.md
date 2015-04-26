## XIV Stats ##

XIV Stats is primarily a script to produce a database of player
information for FFXIV. The information is pulled from directly from the
lodestone. An example PHP file has been included to demonstrate
visualising the statistics. You can also view a live demo of the example
web page by visiting [jonathanprice.org/xiv](https://jonathanprice.org/xiv/).

The aim of this project is to allow people to build their own projects
using this data. For example, creating a website to compare players.

If you would rather download a pre-populated database containing every
player (as of 2015-04-23), please see the "Notes" section below.

The project is inspired by [xivsoul.com](https://xivsoul.com).

# Configuration #

The path for the database to be used is specified on the line beginning
"db_path" in xiv_stats.rb.

# Usage #

The script will collect information on all players with IDs in the specified
range, as shown below:

    ./xiv_stats.rb <lowest ID> <highest ID>

The player ID can be determined by looking at the URL for the lodestone
profile page of a given player.

# Notes #

The script deliberately only retrieves between 1-2 players per second. This
is to avoid excessive load on the lodestone's servers. Due to the slow
execution, a complete copy of the database has been compiled and is avaiable
from the following URL: [Download](https://jonathanprice.org/xiv/players.db)

A simple example PHP web page has been included. This web page draws data
directly from the database and uses it to draw a few charts. Due to the
large amount of data that has to be compiled to produce the charts,
the page takes a very long time to render (around 5 minutes on my server).
If you were planning to embed data from the database in a web page, it 
would be recommended to compile a static copy of the page, and re-compile
it if you re-scan the lodestone. A simple way to compile the page is shown
below:

    php index.php > index.html

# Data Structure #

All information is stored in a single table called "players".

This table contain the following columns:
- id (derived from the player's lodestone profile URL)
- realm
- player_name
- race
- gender
- grand_company
- level_gladiator
- level_pugilist
- level_marauder
- level_lancer
- level_archer
- level_rogue
- level_conjurer
- level_thaumaturge
- level_arcanist
- level_carpenter
- level_blacksmith
- level_armorer
- level_goldsmith
- level_leatherworker
- level_weaver
- level_alchemist
- level_culinarian
- level_miner
- level_botanist
- level_fisher