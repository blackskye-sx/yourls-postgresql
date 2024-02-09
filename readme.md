# DO NOT USE YET
# An unofficial PostgreSQL Driver for YOURLS


This is a fork of a [fork](https://github.com/Flameborn/yourls-sqlite) in an attempt to update it for PostgreSQL

# DOCUMENTATION IN PROGRESS...

## A note on encoding

YOURLS switched to the *UTF8mb4* encoding for the official MySQL database driver for *v1.7.10*. Since SQLite uses *UTF8*, and has no support for the new character encoding format, using this unofficial driver will not allow you to create short URLs with extended characters stored as 4 Bytes, such as emojis.

## What

This is a custom DB layer that allows to use YOURLS with PDO + PostgreSQL. This requires **YOURLS (TBD) 1.8**, not before, not after. See [YOURLS releases](https://github.com/YOURLS/YOURLS/releases).

This is experimental, mostly to show how it should be done, ie without [hacking core file](https://github.com/YOURLS/YOURLS/wiki/Dont-Hack-Core) - see [YOURLS issue #1337](https://github.com/YOURLS/YOURLS/issues/1337) (1337, for real!).

## How

* Drop these files in `/user/`, next to your `config.php` (this is *not* a plugin)
* Update `config.php` using the same parameters/variables as MySQL, but specific to your PostgreSQL database.
* Load YOURLS: the first time, it will create a fresh PostgreSQL DB.
* Have fun

## FAQ

##### *Doesn't work!*
Shut up. I'm still working on it.

##### *Will this break my existing install that uses MySQL?*
Nope! All the data stored in MySQL is untouched (you can test this driver with no SQL server running to be sure) and when you're done, simply delete (or rename) the `db.php` file and you'll get all your original data back from MySQL

## License

(TBD)
Previous developers are ozh, reanimus, and Flameborn, based on their sqlite driver for yourls

