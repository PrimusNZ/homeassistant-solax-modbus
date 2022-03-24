[![hacs_badge](https://img.shields.io/badge/HACS-Default-41BDF5.svg)](https://github.com/hacs/integration)

[![ko-fi](https://www.ko-fi.com/img/githubbutton_sm.svg)](https://ko-fi.com/V7V51QQOL)

[Octopus.Energy 🐙](https://share.octopus.energy/wise-boar-813) referral code. You get £50 credit for joining and I get £50 credit.

# homsassistant-solax-modbus
SolaX Power Modbus custom_component for Home Assistant
Support Modbus over RS485 & TCP

You can have multiple instances of this Integration, just change the default Prefix from SolaX to something else. Ie SolaX Main or SolaX Southwest

Supports:

- Gen2 Hybrid
- Gen3 Hybrid
- Gen4 Hybrid

Gen2, Gen3 & Gen4

- Battery Awaken
- Charge / Discharge rate of battery
- Charger Start / End times
- Charger Use Mode

Gen2 & Gen3

- Allow Grid Charge
- Charge periods in Force Time Use Mode
- Min Battery Capacity

Gen3 & Gen4

- Sensors support the "Energy" Dashboard in 2021.08.x and onwards.

Gen3

- ForceTime Period 1 Max Capacity
- ForceTime Period 2 Max Capacity

Gen4

- Backup Discharge Min SOC
- Backup Nightcharge Upper SOC
- Charge / Discharge rate of battery
- Charge and Discharge Period2 Enable
- Discharger Start / End time
- Export Control User Limit
- Feedin Discharge Min SOC
- Feedin Nightcharge Upper SOC
- Manual Mode Select
- Selfuse Discharge Min SOC
- Selfuse Night Charge Enable
- Selfuse Nightcharge Upper SOC

Untested:
Non Hybrid Models ie Solar PV only
 
# Installation

<B>Prefered Option</B>

You can add this custom_component directly through HACS, if you have HACS installed on your Home Assistant instance.

<B>Alternatively</B>

Copy the folder and contents of solax_modbus into to your home-assistant config/custom_components folder.
You may end up with prerelease code that doesn't function as expected.

<B>Post Instalation</B>

After reboot of Home-Assistant, this integration can be configured through the integration setup UI

Any manual updates / HACS updates require a restart of Home Assistant to take effect.

<B>Inverter never connected to the Cloud / possibly after a firmware update:</B>
- If you can read values, but unable to adjust select / number you need to press the "Unlock Inverter" button.

# Known Issues

1. You can only have one connection to the inverter, so you can't use this and one of my yaml [packages](https://github.com/wills106/homeassistant-config/tree/master/packages) at the same time for writing to registers.
2. Possible Warnings about blocking call in the event loop (in systems with serial modbus connection).
3. Please check the Todo List under discussions for other known issues and what's being worked on.
4. You need to manually add select and number entries to your lovelace card if you manually control your front end.

Gen2, Gen3 & Gen4

<details>
  <summary>Entities to manually add</summary>

- button.solax_battery_awaken
- button.solax_unlock_inverter
- number.solax_battery_charge_max_current
- number.solax_battery_discharge_max_current
- select.solax_charger_end_time_1
- select.solax_charger_end_time_2
- select.solax_charger_start_time_1
- select.solax_charger_start_time_2
- select.solax_charger_use_mode

</details>
 
Gen2 & Gen3

<details>
  <summary>Entities to manually add</summary>
 
- number.solax_battery_minimum_capacity
- select.solax_allow_grid_charge

</details>
 
Gen3

<details>
  <summary>Entities to manually add</summary>

- number.solax_forcetime_period_1_max_capacity
- number.solax_forcetime_period_2_max_capacity

</details>

Gen4

<details>
  <summary>Entities to manually add</summary>

- number.solax_backup_discharge_min_soc
- number.solax_backup_nightcharge_upper_soc
- number.solax_charge_discharge_rate_of_battery
- number.solax_export_control_user_limit
- number.solax_feedin_discharge_min_soc
- number.solax_feedin_nightcharge_upper_soc
- number.solax_selfuse_discharge_min_soc
- number.solax_selfuse_nightcharge_upper_soc
- select.solax_charge_and_discharge_period2_enable
- select.solax_discharger_end_time_1
- select.solax_discharger_end_time_2
- select.solax_discharger_start_time_1
- select.solax_discharger_start_time_2
- select.solax_manual_mode_select
- select.solax_selfuse_night_charge_enable

</details>
