# Notification

You can test your notification configuration by running `npm run test:notification`.

## Desktop

| Environment variable | Description |
|---|---|
| `DESKTOP_NOTIFICATIONS` | Display desktop notifications using [node-notifier](https://www.npmjs.com/package/node-notifier). |
| `PLAY_SOUND` | Play this sound notification if a product is found. Relative path accepted, valid formats: wav, mp3, flac, E.g.: `path/to/notification.wav`, [free sounds available](https://notificationsounds.com/) |

???+ attention
    If you're on Windows, you must have the proper library to run.

## Discord

| Environment variable | Description |
|:---:|---|
| `DISCORD_NOTIFY_GROUP` | Discord group you would like to notify. Can be comma separated |
| `DISCORD_WEB_HOOK` | Discord Web Hook URL. Can be comma separated. Use whole webhook URL |

???+ note
    - If you're using a role, please use `<@&2834729847239842>`
    - If you're using a user, please use `<@2834729847239842>`

## Email and SMS

Default provider is Gmail. If you use a different email provider, you must provide SMTP settings.

| Environment variable | Description |
|:---:|---|
| `EMAIL_PASSWORD` | Email password. (See below for Gmail MFA users) |
| `EMAIL_TO` | Destination Email. Defaults to username if not set. Can be comma separated |
| `EMAIL_USERNAME` | Email address |
| `PHONE_CARRIER` | [Supported carriers](#supported-carriers) for SMS. E.g.: `att` or `att,verizon,google`, email configuration required. If multiple phone numbers are listed, enter a carrier for each phone number |
| `PHONE_NUMBER` | 10 digit phone number(s). E.g.: `1234567890` or `1234567890,0987654321,11112223333`, email configuration required |
| `SMTP_ADDRESS` | IP Address or FQDN of SMTP server |
| `SMTP_PORT` | TCP Port number on which the smtp server is listening for connections. Default: `25` |

???+ attention
    If you use Gmail and have multi-factor authentication (MFA), you will need to create an [app password](https://myaccount.google.com/apppasswords) and use this instead of your Gmail password.

### Supported carriers

| Carrier | Environment variable |
|:---:|:---:|
| AT&T | `att` |
| AT&T Prepaid | `attgo` |
| Bell | `bell` |
| Fido | `fido` |
| Google | `google`|
| Koodo | `koodo` |
| Mint | `mint`|
| Rogers | `rogers` |
| Sprint | `sprint`|
| Telus | `telus`|
| T-Mobile | `tmobile`|
| Verizon | `verizon`|
| Virgin | `virgin`|
| Virgin (CA) | `virgin-ca`|
| Visible | `visible`|

## MQTT

| Environment variable | Description |
|:---:|---|
| `MQTT_BROKER_ADDRESS` | IP address or URL of MQTT Broker, e.g.: `192.168.1.xxx` or `broker.hivemq.com` |
| `MQTT_BROKER_PORT` | Network port of MQTT Broker. Default: `1883` |
| `MQTT_CLIENT_ID` | Unique Client ID (only if required by MQTT Broker), typically not required when only publishing alerts |
| `MQTT_PASSWORD` | MQTT password - only use with MQTT brokers on private networks, if required. Will not be sent over public networks for safety |
| `MQTT_QOS` | QoS level for published alerts to broker (https://www.npmjs.com/package/mqtt#about-qos). Default: `0`, Can be `0`, `1`, or `2` |
| `MQTT_TOPIC` | Topic to publish alerts to. Can include `%store%`, `%series%`, `%brand%`, `%model%` for dynamic topics. Default: `streetmerchant/alert`. E.g.: `nv-alert/%store%/%series%/%brand%/%model%/alert` |
| `MQTT_USERNAME` | MQTT username - (only if required by MQTT Broker) |

## PagerDuty

Obtained in PagerDuty - <Service you want to use> - Integrations

| Environment variable | Description |
|:---:|---|
| `PAGERDUTY_INTEGRATION_KEY` | PagerDuty Events API v2 Integration Key. |
| `PAGERDUTY_SEVERITY` | Severity of PagerDuty events |

## Philips Hue

Generate required keys using [instructions](https://developers.meethue.com/develop/get-started-2/). This will be used for both LAN and cloud access over the official Remote Hue API.

For cloud only usage, instructions to generate are located [here](https://developers.meethue.com/develop/hue-api/remote-authentication/).

| Environment variable | Description |
|:---:|---|
| `PHILIPS_HUE_API_KEY` | Hue Bridge API Key |
| `PHILIPS_HUE_LAN_BRIDGE_IP` | LAN IP Address of your Hue Bridge. LAN only, e.g. `192.168.x.x` |
| `PHILIPS_HUE_LIGHT_IDS` | Light IDs. All lights if not supplied. Can be comma separated, e.g.: `1,2`. See Hue App -> About for IDs |
| `PHILIPS_HUE_LIGHT_COLOR` | Color in RGB Format. Nvidia green if not supplied. Can be comma separated, e.g.: `255,255,255` |
| `PHILIPS_HUE_LIGHT_PATTERN` | Lights will flash for 30 seconds if `blink` is given |
| `PHILIPS_HUE_CLOUD_ACCESS_TOKEN` | Cloud Access Token. Cloud only |
| `PHILIPS_HUE_CLOUD_REFRESH_TOKEN` | Cloud Refresh Token. Cloud only |
| `PHILIPS_HUE_CLOUD_CLIENT_ID` | Cloud Client ID. Cloud only |
| `PHILIPS_HUE_CLOUD_CLIENT_SECRET` | Cloud Client Secret. Cloud only |

> :point_right: Here's a [video demonstration](https://vimeo.com/476083242).

## Pushbullet

Generate token at https://www.pushbullet.com/#settings/account.

| Environment variable | Description |
|:---:|---|
| `PUSHBULLET` | PushBullet API key |

## Pushover

Generate token at https://pushover.net/apps/build.

| Environment variable | Description |
|:---:|---|
| `PUSHOVER_TOKEN` | Pushover access token |
| `PUSHOVER_USER` | Pushover username |
| `PUSHOVER_PRIORITY` | Pushover message priority |

## Slack

| Environment variable | Description |
|:---:|---|
| `SLACK_CHANNEL` | Slack channel for posting |
| `SLACK_TOKEN` | Slack API token |

## Telegram

| Environment variable | Description |
|:---:|---|
| `TELEGRAM_ACCESS_TOKEN` | Telegram access token |
| `TELEGRAM_CHAT_ID` | Telegram chat ID. Can be comma separated, e.g.: `123456789,987654321` |

## Twilio

Token generation can be found at https://twilio.com/console.

| Environment variable | Description |
|:---:|---|
| `TWILIO_ACCOUNT_SID` | Twilio Account SID |
| `TWILIO_AUTH_TOKEN` | Twilio Auth Token |
| `TWILIO_FROM_NUMBER` | Twilio provided phone number to send messages from |
| `TWILIO_TO_NUMBER` | Mobile number to send SMS to |

???+ note
    Include country codes in phone numbers. Example: `+4401234567890`

## Twitter

Generate all Twitter keys at: https://developer.twitter.com/

| Environment variable | Description |
|:---:|---|
| `TWITTER_ACCESS_TOKEN_KEY` | Twitter Token Key |
| `TWITTER_ACCESS_TOKEN_SECRET` | Twitter Token Secret |
| `TWITTER_CONSUMER_KEY` | Twitter Consumer Key |
| `TWITTER_CONSUMER_SECRET` | Twitter Consumer Secret |
| `TWITTER_TWEET_TAGS` | List of hashtags to append to the tweet message, e.g.: `#nvidia #nvidiastock` |

## Twitch

| Environment variable | Description |
|:---:|---|
| `TWITCH_CLIENT_ID` | Twitch client ID |
| `TWITCH_CLIENT_SECRET`| Twitch client secret |
| `TWITCH_ACCESS_TOKEN` | Twitch access token |
| `TWITCH_REFRESH_TOKEN` | Twitch refresh token |
| `TWITCH_CHANNEL` | Twitch channel |
