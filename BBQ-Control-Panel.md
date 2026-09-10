# BBQ Pit Control Panel

Goal:  convert the ESPHome configuration in this repo located at guition-esp32-p4-jc1060p470/package.yaml to create a BBQ pit controller out of the 
ESP32-P4-JC1060P470 device

entities:
* climate.bbq_esphome_esphome_bbq_pit_controller
  primary climate controller (heating only)
  state values:  off / heat
  attributes:
  * hvac_modes (off / heat)
  * min_temp
  * max_temp
  * target_temp_step
  * current_temperature
  * temperature (setpoint)
  * hvac_action (off / idle / heat)

* sensor.bbq_esphome_esphome_bbq_pit_temperature
* sensor.bbq_esphome_esphome_bbq_pit_fan_output

Use ideas/master-ac-display.yaml as inspiration
See pictures at ideas/climate_off.jpg & ideas/climate_on.jpg



The top-level ESPHome config file looks like this and refers to the package file in this repo:
```
# ESP32-P4-JC1060P470
substitutions:
  name: "bbq-control-panel"
  friendly_name: "BBQ Control Panel"
  room: "Patio"

# Wifi Setup
wifi:
  ssid: Savage
  password: *********
  use_address: 10.4.1.103

api:

# Packages
packages:
  setup:
    url: https://github.com/s4v4g3/esphome-lvgl/
    file: guition-esp32-p4-jc1060p470/package.yaml
    refresh: 1sec
```    