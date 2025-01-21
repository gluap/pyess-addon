<!-- https://developers.home-assistant.io/docs/add-ons/presentation#keeping-a-changelog -->

## 2.0.8
- Fix units for things that contain "current" in their path but are actually not currents (in amps) but just current values (possibly in Watt Hours)

## 2.0.7
- Improve ha-supervised support

## 2.0.6
- Pull in a fix from pyess

## 2.0.5
- Parametrize update interval

## 2.0.4
- Add translations.
- Adapt stuff according to repo readme

## 2.0.3
- Update to pull in new version of pyess to create a "LG ESS" device to contain the energy sensors.

## 2.0.2
- Update to pull in new version of pyess to add "total_increasing" state class to more Wh metering endpoints

## 2.0.1
- Update to pull in new version of pyess to add "total_increasing" state class to Wh metering

## 2.0.0

- Initial version - has the Version number 2.0.0 because I had to increment after using the homeassistant default "1.2.0" during development.
