# Homey harmony hub

This application adds support for the Logitech Harmony Hub to Homey. Control the available devices and/or activities inside a Homey flow, voice commands or the homey app.

Make sure that Homey is connected to the same network as your Logitech Harmony Hub(s) and the app will autodiscover your hub(s). 

> Important: This app uses a local api available on your Logitech Harmony Hub that is undocumented and unsupported by Logitech. If Logitech decides to remove this api in a firmware upgrade this app will stop working.

## Donations
If you like the work on this project please consider a donation. Of course, this is optional and you should in no way feel obligated to send a donation. ~~The donations will be spent on buying a second Harmony Hub to support me testing a multi-hub situation.~~ The donations will be spent on buying a second Homey to use as a development Homey which supports me to keep this app running on future firmware versions of Homey.

[<img src="https://www.paypalobjects.com/en_GB/i/btn/btn_donate_SM.gif">](https://www.paypal.com/cgi-bin/webscr?cmd=_s-xclick&hosted_button_id=8LWS6UKUCHJNC)

# Index
  * [Supported devices](#supported-devices)
  * [Supported languages](#supported-languages)
- [Drivers](#drivers)
  * [Harmony Device driver](#harmony-device-driver)
  * [Harmony Activity driver](#harmony-activity-driver)
- [Capabilities](#capabilities)
  * [OnOff](#onoff)
  * [VolumeUp/VolumeDown/VolumeMute](#volumeup-volumedown-volumemute)
  * [ChannelUp/ChannelDown](#channelup-channeldown)
- [Flow cards](#flow-cards)
  * [Triggers (when)](#triggers--when-)
  * [*Application*](#-application-)
      - [Activity starting](#activity-starting)
      - [Activity started](#activity-started)
      - [Activity stopped](#activity-stopped)
      - [Hub inactive](#hub-inactive)
  * [*Device and activity*](#-device-and-activity-)
      - [Turned on](#turned-on)
      - [Turned off](#turned-off)
  * [Conditions (and)](#conditions--and-)
  * [*Application*](#-application--1)
      - [Activity is/is't matched](#activity-is-is-t-matched)
  * [*Device and activity*](#-device-and-activity--1)
      - [Is on / Is off](#is-on---is-off)
  * [Actions (then)](#actions--then-)
  * [*Application*](#-application--2)
      - [Start activity](#start-activity)
      - [Stop activity](#stop-activity)
  * [*Device and activity*](#-device-and-activity--2)
      - [Turn on](#turn-on)
      - [Turn off](#turn-off)
      - [Toggle on or off](#toggle-on-or-off)
      - [Mute the volume](#mute-the-volume)
      - [Unmute the volume](#unmute-the-volume)
      - [Turn the volume up](#turn-the-volume-up)
      - [Turn the volume down](#turn-the-volume-down)
      - [One channel up](#one-channel-up)
      - [One channel down](#one-channel-down)
      - [Send command (device exlusive)](#send-command--device-exlusive-)
- [(Voice) commands](#-voice--commands)
- [Version History](#version-history)
    + [v1.5.x](#v15x)
    + [v1.4.x](#v14x)
    + [v1.3.x](#v13x)
    + [v1.2.x](#v12x)
    + [v1.1.x](#v11x)
    + [v1.0.0](#v100)

## Supported devices
- Any **device** available on your Logitech Harmony Hub.
- Any **activity** available on your Logitech Harmony Hub.

## Supported languages
- Dutch
- English

# Drivers

To communicate with your Logitech Harmony Hub this app uses drivers. When adding a device you can choose between 2 drivers.

## Harmony Device driver

This driver allows you to pair devices that are synchronised to your Logitech Harmony Hub e.g.:

![Logitech Harmony devices](https://github.com/jreenen/com.jreenen.homeyharmonyhub.documentation/blob/master/assets/images/documentation/Harmony-devices.JPG?raw=true)

Once paired you can use this device in flows or control it from the Homey app.

## Harmony Activity driver

This driver allows you to pair activities that are synchronised to your Logitech Harmony Hub e.g.:

![Logitech Harmony activities](https://github.com/jreenen/com.jreenen.homeyharmonyhub.documentation/blob/master/assets/images/documentation/Harmony-activities.JPG?raw=true)

Once paired you can use this activity in flows or control it from your Homey app.

# Capabilities

During the pairing process the capibilities of devices and activities will get mapped to Homey capabilities. 

## OnOff
Capability for turning a device or activity on or off.

## VolumeUp/VolumeDown/VolumeMute
Capability for controlling the volume level of a device or activity.

## ChannelUp/ChannelDown
Capability for controlling the current channel of a device or activity.

# Flow cards
Flowcards can be used to build flows in Homey's flow editor.

## Triggers (when)

*Application*
-------------

To use the application cards select 'Homey Harmony Hub' in the 'When' column.

#### Activity starting
Every time an activity is about to start on your Logitech Harmony Hub this card will trigger. It provides 2 tags:
- hub, this tag contains the hub name on which the activity is about to start.
- activity, this tag contains the activity name of the activity that is about to start.

#### Activity started
Every time an activity is started on your Logitech Harmony Hub this card will trigger. It provides 2 tags:
- hub, this tag contains the hub name on which the activity is started.
- activity, this tag contains the activity name of the activity that is started.

#### Activity stopped
Every time an activity is stopped on your Logitech Harmony Hub this card will trigger. It provides 2 tags:
- hub, this tag contains the hub name on which the activity is started.
- activity, this tag contains the activity name of the activity that is started.

#### Hub inactive
This card can trigger if the hub is not active for an interval you choose:
-  5 minutes
- 10 minutes
- 15 minutes
- 30 minutes
-  1 hour
-  2 hours
-  4 hours
-  8 hours

It provides the name of the hub that is inactive as a tag.


*Device and activity*
-------------------
#### Turned on
Every time the selected device or activity is turned on this card will trigger.

#### Turned off
Every time the selected device or activity is turned off this card will trigger.

## Conditions (and)

*Application*
-------------
#### Activity is/is't matched
This card can be used to check if an activity is equal or not equal to a specified activity. Although you can type in the activity name by hand I would suggest using a predefined activity tag (e.g. generated by the Activity started application trigger card).

*Device and activity*
---------------------
#### Is on / Is off
This card can be used to check if a specific device or activity is turned on or off.

## Actions (then)

*Application*
-------------
#### Start activity
This card will start a selected activity on a selected hub.

#### Stop activity
This card will stop the current activity on a selected hub.

*Device and activity*
--------
#### Turn on
This card will turn on a specific device or activity.

#### Turn off
This card will turn off a specific device or activity.

#### Toggle on or off
This card will toggle the onoff state for a specific device or activity.

#### Mute the volume
This card will mute the volume for a specific device or activity.

#### Unmute the volume
This card will unmute the volume for a specific device or activity.

#### Turn the volume up
This card will turn the volume up for a specific device or activity.

#### Turn the volume down
This card will turn the volume down for a specific device or activity.

#### One channel up
This card will switch one channel up for a specific device or activity.

#### One channel down
This card will switch one channel down for a specific device or activity.

#### Send command (device exlusive)
With this card you can send a command registered in your Logitech Harmony Hub to your device (e.g. input hdmi 1, record program...). The logitech harmony hub is grouping this kind of command so first specify the group and then the command you want to have executed. You can also specify the ammount of times this command should be repeated where 0 is only one time 1 is executing the same command twice etc..

# (Voice) commands

- (Ok Homey,) Turn on [device or activity name]
- (Ok Homey,) Turn off [device or activity name]
- (Ok Homey,) Mute [device or activity name]
- (Ok Homey,) Unmute [device or activity name]
- (Ok Homey,) Volume up [device or activity name]
- (Ok Homey,) Volume down [device or activity name]
- (Ok Homey,) Channel up [device or activity name]
- (Ok Homey,) Channel down [device or activity name]

# Version History

### v1.5.x
- New option to add activities as a device.
- If an activity is recognized as a television activity it will use the Homey built-in TV class and e.g. let Homey respond to: Ok Homey, turn on tv
- Capabilities for on/off, channel up/down, volume up/down/mute are now mapped on devices and activities that has support for them.
- If your hub for some reason goes offline all attached devices and activities will be set to unavailable until it is back online.
- When you add a device or activity on the Logitech harmony app those changes will get synced, so an app restart is no longer needed when changes occur on the hub.
- Added allot of new icons to use on devices, almost every device type has its own icon now. If you already have a device paired and want to use the new icon you unfortunately have to delete and re-add it.
- An app settings options that makes it possible to send me a diagnostic report if you are experiencing a hard to trace bug in this app (only use this when i ask for it)

### v1.4.x
- App is rewritten to utilize the websockets API instead of XMPP (which got disabled by logitech). Again a big thank you to @denniedegroot for your big help in this.

### v1.3.x

- Added starting activity trigger to be informed an activity is about to start.
- Added a repeat argument to the send command action (e.g. for adjusting the volume by more than just one step).
- Added an inactivity trigger to be informed when the hub is being inactive for a specified period.
- Added a activity comparing condition

A special thanks to @denniedegroot who added on/off functionality for smart home devices and will help me on this project whenever time allows him to.

### v1.2.x

- Instead of always using the power toggle command use the power on and power off when they are available and fallback to the power toggle command when they are not available. This solves an issue with devices that don't support the power toggle command
- Fixed an issue where on powering off an activity, an activity started trigger got raised on the previous activity instead of an activity stopped trigger.
- For improved stability and future features, a new connection library has been written for the Homey Harmony App. 
- If an activity has been started/stopped by an external source (e.g. the Logitech Harmony Remote), the app picks up on this event and updates the device states accordingly and triggers the applicable flow cards.
- You can now use a flow condition card for your device to check if it is/isn't turned on.

### v1.1.x
- Pairing of devices connected to the harmony hub
- A mobile card supporting the power toggle functionality of the device
- An action card for sending a specific command to the Harmony device using homey flows.
- Action cards for starting/stopping a hub activity
- Trigger cards for device is turned on/off
- Trigger cards for activity is started/stopped
- Syncing the device on-off state based on the current hub activity

### v1.0.0 

- Initial release (never hit the Athom store)
