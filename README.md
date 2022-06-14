# homeassistant-aerogarden
This is a custom component for [Home Assistant](http://home-assistant.io) that adds support for the Miracle Grow [AeroGarden](http://www.aerogarden.com) Wifi hydroponic gardens.

## Background
This was developed without collaboration with AeroGarden, and as of publication, there is no documented public API. This implementation was forked from that of ksheumaker after it was declared unmaintained, who in turn took inspiration and code from the code in this [forum post by epotex](https://community.home-assistant.io/t/first-timer-trying-to-convert-a-working-script-to-create-support-for-a-new-platform).

Currently, the code is setup to query the AeroGarden servers every 30 seconds.

## Tested Models

* Harvest Wifi

(Other models are expected to work, since this queries AeroGarden's cloud service rather than the garden directly. Please confirm success in an issue if you use another model, so that the documentation may be updated.)

## Setup
This repository is designed to be added using HACS as a custom integration. It can, however, be installed manually.

## Configuration
Add the following snippet into your ```configuration.yaml```.  Replace [EMAIL] and [PASSWORD] with the account information you use in the AeroGarden phone app.

```

aerogarden:
    username: [EMAIL]
    password: [PASSWORD]

```

## Data available
The component supports multiple gardens, and multiple sensors will be created for each garden.  [GARDEN NAME] will be replaced by whatever you named the garden in the AeroGarden app.

### Light
* light.aerogarden_[GARDEN NAME]_light
  
### Binary Sensors (on/off) 
* binary_sensor.aerogarden_[GARDEN NAME]_pump
* binary_sensor.aerogarden_[GARDEN NAME]_need_nutrients
* binary_sensor.aerogarden_[GARDEN NAME]_need_water
  
### Sensors
* sensor.aerogarden_[GARDEN NAME]_nutrient
* sensor.aerogarden_[GARDEN NAME]_planted

### Sample screenshot
![Screen Shot](https://raw.githubusercontent.com/alexiswatson/homeassistant-aerogarden/master/screen_shot.png)
  
## Roadmap
1. Test and confirm integration with HACS.
2. Code cleanup.
3. Toggling the light is reported to be not as smooth as desired--investigate.

