# `src`

This directory contains three notebooks:

## `data_visualization`

This code imports the latest luxmeter data, as well as the temperature datafile of your choosing (which is named in the format 'month_startdate-enddate'). The dataframe is formatted to get rid of errors, and a graph with selected data is produced.

The columns of the temperature data imported from the thermometer are named:

|    Date   |    Time   |   T1   |   T2   |   T3   |   T4   |
|-----------|-----------|--------|--------|--------|--------|

The columns of the light data imported from the luxmeter are named:

|    Place   |    Date   |   Time   |   Value   |   Unit   |
|------------|-----------|----------|-----------|----------|

## `model_building`

This code uses the main tank temperature data which was recorded on thermocouple $T_2$, to parametrise a solar water heater model by determining the correctional factor $k$ and overall heat transfer coefficient U which best fits the measured data.

The measured temperature data goes through a manual preselection because some of the recorded data is not representative of the solar water heater functioning properly - due to me switching parts or performing maintenance on the system. These temperature files are found in the folder Temperature_Data/Training_Data

Following this, the thermometer data is lined up with the light data according to their timestamps using the function align_and_merge_temp_lux. The function iterates through the chosen temperature dataframes to create a larger temperature and light dataframe which can be used for parameter search.

Acquiring more temperature data will enable more precise determination of the parameters $k$ and $U$.

## `simulation_analysis`

This code expands the solar water heater model to include pasteurisation dynamics; with the inclusion of parameters $T_{\rm flow}$, $T_{\rm past}$, $e$, $x$, and $Main_tank_cap$.

The model is used to simulate pasteuriser operation in Narok and Homa Bay, thanks to weather data made available by the World Bank Group for 2020 and 2021. The original dataset, description and headers can be found [here](https://energydata.info/dataset/kenya-solar-radiation-measurement-data).

The columns of the dataframes that are useful for simulation are:

|    time   |   ghi_pyr_1   |   air_temperature   |
|---|---|----|