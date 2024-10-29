# `temperature`

This data contains the temperaure measurements in degree Celcius. The sampling frequency is every 10 minutes.

The columns of the temperature data imported from the thermometer are named:

|    Date   |    Time   |   T1   |   T2   |   T3   |   T4   |
|-----------|-----------|--------|--------|--------|--------|

- T1: Outlet Block Temperature - located in the PPR piping right before the temperature control, it is used as an indicator of when the effluent is going to flow out of the system.
- T2: Main Tank Temperature - located inside a metal sleeve that is inserted into the main tank for the purpose of temperature monitoring. This temperature can inform on how well the solar water heater performs when capturing radiation.
- T3: Raw Effluent Temperature - located at the outlet of the AD balloon.
- T4: Heat Exchange Temperature - located right after the heat exchanger, it can be used to determine the temperature difference that occurs due to preheating via heat exchanger, and is needed to calculate the efficiency of the heat exchange.

## `all_data`

Inside the folder 'all_data' can be found the temperature files collected from the SEFRAM thermometer, named in the format `month_startdate-enddate`, over the months of May and June 2024:
- `05_11-14.csv`
- `05_18-19.csv`
- `05_20-21.csv`
- `05_21-22.csv`
- `05_22-23.csv`
- `05_24-24.csv`
- `05_24-27.csv`
- `05_29-31.csv`
- `05_31-01.csv`
- `06_01-03.csv`
- `06_06-10.csv`
- `06_11-12.csv`
- `06_12-17.csv`
- `06_17-14.csv`
- `06_24-25.csv`
- `06_25-01.csv`

## train_data

The directory `train_data` is a subgroup of `all_data`, containing the manually-selected files. This is because some of the recorded data is not representative of the solar pasteuriser functioning properly - due to me switching parts or performing maintenance on the system.

The files in `train_data` are used to parametrise the python model of the solar pasteuriser.