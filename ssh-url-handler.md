# How to handle ssh urls with iterm2

In order to handle the `ssh://fancy-host.domain.com` style urls in iTerm2 you just need to have a profile to handle it 

## iTerm2 Setup
So to get started create a profile in iterm2 for handling your man pages.

1) Select the URL Schema for `ssh`
2) Change the command to the following `ssh $$HOST$$`

This should now ssh to the host 