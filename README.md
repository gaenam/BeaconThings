# BeaconThings

BeaconThings allows you to integrate iBeacons into your SmartThings smart home
to enable more precise presence/location sensing.

## Features
With BeaconThings, you can get more reliable, and more specific location
information. Spread some beacons around your home, register them with
BeaconThings, and it will tell SmartThings when you're nearby. For each
BeaconThing your register, a device is added to SmartThings that can be used
with SmartRules or custom SmartApps, to trigger events.

BeaconThings are organized into "Places" and "Areas". An area is one specific
location, like "Kitchen", and is specified by one specific beacon. Areas map to
the "minor" field of the beacon. A place is something like "Home", or "Work",
and would typically contain multiple areas. This maps to the "major" field of
the iBeacon. When setting up your home, you'll configure your beacons with the
BeaconThings UUID (specified in the app), and then choose a unique major value
for each place, and unique minor values for each area. When any of the areas in
one place are detected, then that place is "present".

Once you've registered your BeaconThings, you never need to open the app again.
It will do its work 100% in the background with no user interaction required.

To minimize battery drain, BeaconThings only uses iBeacon monitoring. This means
that it won't tell you whether you are inches from the beacon, or 20 feet away,
only whether or not the beacon is detected in range. When you need to detect a
limited range, just use an iBeacon with configurable power settings.

## Future Work

The current implementation uses iBeacons like a simple presence sensor, but this
is not using the beacons to their full potential. Beacons can be used to
identify when a particular device is in a particular area. A presence sensor is
not enough, since it only has two states, present, or not present. There is no
distinction between multiple users being present or not present. To fully
utilize the beacons, we need to pair a device or user with a beacon. There is
some added complexity due to two possible use cases:

1. Beacons are stationary and a person's phone detects nearby beacons.
(Beacons are locations, devices are users)
2. Phone/tablet is stationary, and detects a mobile beacon worn by a user.
(Devices are locations, beacons are users)

In both cases, ideally users of the app would define a user, and then detect
nearby locations, and use them to trigger actions.
