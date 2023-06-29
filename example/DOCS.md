# Home Assistant Add-on: pyess

This is an addon for coupling homeassistant with LG ESS type photovoltaic inverters.

This addon depends on the mqtt/mosquitto addon being set up. Together with mosquitto it facilitates setting up ``essmqtt`` from [``pyess``](https://github.com/gluap/pyess). 

## How to use
### Determine your ESS password From an Android mobile:
1. Download [Pydroid 3](https://play.google.com/store/apps/details?id=ru.iiec.pydroid3&hl=de&gl=US). When opening the app skip the paid plans and use the ad-based plan.
2. In the app open the terminal
3. in the terminal run
   ```
   pip install pyess
   ```
4. connect to the wifi of your ess
5. in the terminal run
   ```
   esscli --action get_password
   ```
6. write down your password

### Configure this addon
On the configuration page, enter the required information:
- the IP-Address or hostname of your ESS
- the password from above
- mqtt username and password will be passed by the mqtt addon.

- Decide which values from the list below should be announced as sensors to homeassistant and enter them as a long line of comma-separated values without spaces (you can prepare it in a text editor). Follow the configuration example you see on the config page.

```
    ess/home/statistics/pcs_pv_total_power 0
    ess/home/statistics/batconv_power 190
    ess/home/statistics/bat_use 1
    ess/home/statistics/bat_status 2
    ess/home/statistics/bat_user_soc 81.25
    ess/home/statistics/load_power 191
    ess/home/statistics/load_today 0.0
    ess/home/statistics/grid_power 1
    ess/home/statistics/current_day_self_consumption 0.0
    ess/home/statistics/current_pv_generation_sum 0
    ess/home/statistics/current_grid_feed_in_energy 0
    ess/home/direction/is_direct_consuming_ 0
    ess/home/direction/is_battery_charging_ 0
    ess/home/direction/is_battery_discharging_ 1
    ess/home/direction/is_grid_selling_ 0
    ess/home/direction/is_grid_buying_ 1
    ess/home/direction/is_charging_from_grid_ 0
    ess/home/operation/status start
    ess/home/operation/mode 1
    ess/home/wintermode/winter_status on
    ess/home/pcs_fault/pcs_status pcs_ok
    ess/common/PV/brand LGE-SOLAR
    ess/common/PV/capacity 5850
    ess/common/PV/pv1_voltage 26.500000
    ess/common/PV/pv2_voltage 26.700001
    ess/common/PV/pv1_power 0
    ess/common/PV/pv2_power 0
    ess/common/PV/pv1_current 0.110000
    ess/common/PV/pv2_current 0.000000
    ess/common/PV/today_pv_generation_sum 0
    ess/common/PV/today_month_pv_generation_sum 438389
    ess/common/BATT/status 2
    ess/common/BATT/soc 81.2
    ess/common/BATT/dc_power 190
    ess/common/BATT/winter_setting on
    ess/common/BATT/winter_status on
    ess/common/BATT/safty_soc 20
    ess/common/BATT/today_batt_discharge_enery 135
    ess/common/BATT/today_batt_charge_energy 0
    ess/common/BATT/month_batt_charge_energy 72692
    ess/common/BATT/month_batt_discharge_energy 51250
    ess/common/GRID/active_power 2.790000
    ess/common/GRID/a_phase 230.899994
    ess/common/GRID/freq 49.959999
    ess/common/GRID/today_grid_feed_in_energy 0
    ess/common/GRID/today_grid_power_purchase_energy 0
    ess/common/GRID/month_grid_feed_in_energy 266094
    ess/common/GRID/month_grid_power_purchase_energy 7037
    ess/common/LOAD/load_power 191
    ess/common/LOAD/today_load_consumption_sum 135
    ess/common/LOAD/today_pv_direct_consumption_enegy 0
    ess/common/LOAD/today_batt_discharge_enery 135
    ess/common/LOAD/today_grid_power_purchase_energy 0
    ess/common/LOAD/month_load_consumption_sum 157890
    ess/common/LOAD/month_pv_direct_consumption_energy 99603
    ess/common/LOAD/month_batt_discharge_energy 51250
    ess/common/LOAD/month_grid_power_purchase_energy 7037
    ess/common/PCS/today_self_consumption 0.0
    ess/common/PCS/month_co2_reduction_accum 311256
    ess/common/PCS/today_pv_generation_sum 0
    ess/common/PCS/month_pv_generation_sum 438389
    ess/common/PCS/today_grid_feed_in_energy 0
    ess/common/PCS/month_grid_feed_in_energy 266094
    ess/common/PCS/pcs_stauts 3
    ess/common/PCS/feed_in_limitation 70
    ess/common/PCS/operation_mode 0
```