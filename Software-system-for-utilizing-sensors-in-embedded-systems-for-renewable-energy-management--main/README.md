# Software system for utilizing sensors in embedded systems for renewable energy management

This project presents a Smart Energy Management System (SEMS) designed to optimize the integration of renewable and non-renewable energy sources. It includes a sophisticated control system for energy flow management based on real-time weather data, aiming to reduce carbon emissions and enhance energy efficiency.

## Description

SEMS encompasses the following key capabilities:

- Real-time weather data retrieval from an external API.
- Dynamic selection of optimal renewable energy sensors based on weather conditions.
- Analysis of renewable energy production and emissions savings.
- Efficient storage of excess renewable energy in battery storage.
- Controlled release of stored energy to meet demand during low renewable production.
- Future predictions for renewable energy emissions reductions.

It aims to contribute to grid stability and maximize the utilization of renewable energy sources.

## Code Structure

The main components of the code include:

- `Sensor` classes: Provide real-time renewable energy data.
- `EnergyManagementSystem`: Analyzes sensor data to calculate energy and emissions.
- `BatteryStorage`: Stores excess renewable energy and releases it when required.
- `SmartGridController`: Manages energy flow between renewable sources and the battery.
- `FutureEmissionsPredictor`: Predicts future emissions savings through 2050.

### Component Architecture:

1. **Weather API:**
   - **Responsibility:** Fetches real-time weather data.
   - **API Used:** Open Meteo API (`https://api.open-meteo.com/v1/forecast`).

2. **Sensors:**
   - **Types:**
     - Solar Sensor (e.g., Solar panels)
     - Wind Sensor (e.g., Wind turbines)
     - Hydro Sensor (e.g., Hydroelectric sensors)
     - Other Sensor (Generic renewable sensor)
     - Non-Renewable Sensor (e.g., Coal-based sensors)
   - **Responsibility:** Collects real-time energy data.
   - **Methods:**
     - `get_real_time_data()`: Simulates energy values.
     - `get_adapted_data(weather_condition)`: Adjusts data based on weather conditions.

3. **Energy Management System (EMS):**
   - **Responsibility:** Manages energy production, compliance checks, and emissions calculation.
   - **Methods:**
     - `calculate_total_energy(weather_condition)`: Calculates total energy generated.
     - `analyze_energy_data(weather_condition)`: Analyzes energy data based on weather conditions.
     - `check_compliance()`: Checks compliance with emission and safety standards.

4. **Battery Storage:**
   - **Responsibility:** Stores excess energy and releases stored energy when needed.
   - **Methods:**
     - `store_energy(energy)`: Stores energy in the main or auxiliary storage.
     - `release_energy(energy_needed)`: Releases stored energy.
     - `check_storage_status()`: Checks if the storage is full.
     - `adjust_storage_levels()`: Adjusts storage levels in case of overcharge.

5. **Smart Grid Controller:**
   - **Responsibility:** Manages energy flow between the energy system and battery storage.
   - **Methods:**
     - `manage_energy_flow(demand, weather_condition)`: Manages energy flow based on demand and weather conditions.

6. **System Monitor:**
   - **Responsibility:** Logs system events.
   - **Methods:**
     - `log(message)`: Logs system messages.
     - `get_logs()`: Retrieves system logs.

7. **Future Emission Predictor:**
   - **Responsibility:** Predicts future CO2 emission savings.
   - **Methods:**
     - `predict_future_savings(degree)`: Predicts future savings using polynomial regression.

8. **Main Execution (Script):**
   - **Responsibility:** Orchestrates the entire system, handles user input, and executes the simulation.
   - **Methods:**
     - `main()`: Main execution function that simulates the energy system.

### Datasets:
- **Weather Data:**
  - **Source:** Open Meteo API (`https://api.open-meteo.com/v1/forecast`).
  - **Frequency:** Real-time updates.

### Frequency:
- **Real-time Simulation:**
  - The system simulates real-time energy data and weather conditions.
  - Iterations are controlled by a synchronous loop with a specified fetch interval.

### State Variables:
- **Weather Condition:**
  - Represents the current weather condition affecting energy production.
- **Energy Demand:**
  - Represents the demand for energy.
- **Stored Energy (Main Battery and Auxiliary Storage):**
  - Represents the current energy stored in the main battery and auxiliary storage.
- **Emission Reduction:**
  - Represents the calculated reduction in CO2 emissions.


## Running the Code

To run the smart grid analytics:

1. Ensure Python 3.x and the required libraries are installed.
2. Obtain API keys for weather and emissions data sources.
3. Update `api_url` and other constants as needed.
4. Run `python smart_grid.py`.
5. Input latitude and longitude when prompted.
6. Review energy production, storage, and predicted emissions data.

## Output

The main outputs include:

- Real-time weather conditions.
- Renewable energy produced.
- Emissions from renewable vs non-renewable sources.
- Excess renewable energy stored and released.
- Predicted renewable energy emissions reductions through 2050.

## Visualization

SEMS includes a visualization module based on Matplotlib for predicting CO2 emission savings. This provides an insightful graphical representation of the impact of renewable energy over time.

## Customization

To customize the system:

- Add additional sensor models.
- Update the emissions factor dictionary.
- Modify the predictor model algorithm.
- Integrate with other weather and emissions datasets.

## Acknowledgements

SEMS acknowledges the following libraries:

- NumPy
- Pandas
- Scikit-Learn
- Matplotlib
- Requests

## Contributing

Contributions are welcome. Please fork the repository, create a feature branch, commit your changes, and open a pull request.
