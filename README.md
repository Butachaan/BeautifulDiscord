BeautifulDiscord
================

Simple Python script that adds CSS hot-reload to Discord.

![demo gif](http://i.imgur.com/xq4HS5f.gif)

## Motivation

I wanted custom CSS injection for Discord, with no JavaScript add-ons or anything.
That's BeautifulDiscord.

If you want JS, you can either:
- Use [BetterDiscord](https://github.com/Jiiks/BetterDiscordApp)
- Make your own thing!

You could also fork this repo and add it, it's not that big of a stretch.
I just didn't add it because it's not what I want to do here.

## Usage

Just invoke the script when installed. If you don't pass the `--css` flag, the stylesheet
will be placed wherever the Discord app resources are found, which is not a very convenient
location.

**NOTE:** Discord has to be running for this to work in first place.
The script works by scanning the active processes and looking for the Discord ones.

(yes, this also means you can fool the program into trying to apply this to some random program named Discord)

```
$ beautifuldiscord --css C:\mystuff\myown.css
0: Found DiscordPTB.exe
1: Found DiscordCanary.exe
Discord executable to use (number): 1

Done!

You may now edit your C:\mystuff\myown.css file,
which will be reloaded whenever it's saved.

Relaunching Discord now...
$
```

Pass the `--revert` flag to remove the extracted `app.asar` (it's the `resources/app` folder)
and rename `original_app.asar` to `app.asar`. You can also do this manually if your Discord
install gets screwed up.

```
$ beautifuldiscord --revert
0: Found DiscordPTB.exe
1: Found DiscordCanary.exe
Discord executable to use (number): 1
Reverted changes, no more CSS hot-reload :(
$
```

You can also run it as a package - i.e. `python3 -m beautifuldiscord` - if somehow you cannot
install it as a script that you can run from anywhere.

## Installing

```
python3 -m pip install -U https://github.com/leovoel/BeautifulDiscord/archive/master.zip
```

Usage of a virtual environment is recommended, to not pollute your global package space.

## Requirements

- Python 3.x (no interest in compatibility with 2.x, untested on Python 3.x versions below 3.4)
- `psutil` library: https://github.com/giampaolo/psutil

Normally, `pip` should install any required dependencies.

## Themes

Some people have started a theming community over here:
https://github.com/beautiful-discord-community/resources/

They have a Discord server as well:
https://discord.gg/EDwd5wr

## More GIFs

![demo gif](http://i.imgur.com/w0bQOJ6.gif)
