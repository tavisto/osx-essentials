# How to handle man page urls with iterm2

In order to handle the `x-man-page://1/bash` style urls in iTerm2 I had to do some trickery.

## iTerm2 Setup
So to get started create a profile in iterm2 for handling your man pages.

1) Select the URL Schema for `x-man-page`
2) Change the command to the following `~/bin/x-man-page.sh $$HOST$$$$PATH$$`

This should now try and call a script in your home directory that will do the parsing for us.

## The script

I have written a quick little script to help me parse the url:
```
URL=$1
SECTION=$(echo $URL | awk -F '/' '{print $1}')
COMMAND=$( echo $URL | awk -F '/' '{print $2}' )
man $SECTION $COMMAND
```
Place that wherever you like to keep local scripts. I use `~/bin/x-man-page.sh`

## Enjoy!
Click here for the [bash](x-man-page://1/bash) man page to test it out!