# HAMoesTrvAutomations

My Home Assistant Automations for Moes TRV BRT-100.

## Calibrate TRV external temperature

This blueprint uses external temperature sensor readings and updates the local calibration of selected TRVs so it shows the same temperature.

It supoprt multiple TRVs if you have one room with more of them.

Parameters:

- external temperature sensor
- list of TRVs
- offset_factor
    - This adds another offset to calculated calibration
        - calculated as offset_factor * (actual_temperature - target_temperature)
    - Moes TRV work with whole celsius only. If you set target temperature e.g. to 22, it effectively turn itself off when it reads 23, sometimes even 24.
    - by this offset you can effectively make TRV to keep the real target temperature
    - setting to 0 means not use this offseting at all.

I took https://gist.github.com/bruvv/8bb92c251f17a0ccd64b4859e9267057 as an inspiration for this blueprint.
