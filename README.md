irssi-pushover
==============
Originally by [Marcus Carlsson](https://github.com/xintron/irssi-pushover)

Plugin for [irssi](https://irssi.org/) IRC client to send push notifications
using [Pushover](https://pushover.net/).

This allows you to be notified when someone messages/mentions you on IRC,
optionally only when `tmux` is detached.

## Installation

- [Create an API token](https://pushover.net/apps/clone/irssi)
- Fetch this Git repository:
  - `git clone https://github.com/pushoverapp/irssi-pushover`
- Copy `pushover.pl` to `~/.irssi/scripts`, optionally symlink it into `scripts/autorun`.
  - `cd irssi-pushover`
  - `cp pushover.pl ~/.irssi/scripts/`
  - `cd ~/.irssi/scripts/autorun; ln -s ../pushover.pl .`
- Within irssi:
  - `/load autorun/pushover.pl`
  - `/set pushover_user_key YOUR_PUSHOVER_USER_KEY` (which can be found on [your dashboard](https://pushover.net/dashboard))
  - `/set pushover_api_token YOUR_PUSHOVER_API_TOKEN` created in step 1
  - `/save`
  - `/pushtest hello world` to test sending

## Dependencies

 - `Crypt::SSLeay` / `libcrypt-ssleay-perl` installed

## Optional Settings

  - `/pushignore help` - get started in populating the ignore list

  - `/set pushover_debug 1` - enable verbosity
  - `/set pushover_ignore 1` - turn on ignore configurability
  - `/set pushover_ignorechannels` - a space separated list of channels to ignore
  - `/set pushover_ignorefile` - set the path to the saved ignored list file
  - `/set pushover_only_if_away [on|off]` - if `on`, only send Pushover messages when `/away`
  - `/set pushover_sound SOUND` - chosen from the [sound list](https://pushover.net/api#sounds), otherwise defaults to your device's default sound
  - `/set pushover_tmux_only_if_unattached [on|off]` - if `on`, only send Pushover messages when irssi is run inside of tmux and tmux is attached
  - `/set pushover_tmux_session_name SESSION_NAME` - the tmux session that irssi must be run under
  - `/set pushover_url YOUR_URL` - a URL to include in each push message, possibly to open an app on your mobile device
  - `/set pushover_url_title YOUR_URL_TITLE` - a URL title to include in each push message
