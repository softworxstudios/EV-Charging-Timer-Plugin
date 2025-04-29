
# EV Charger Charging Automation Blueprint

This Home Assistant blueprint manages the EV Charger charging process with progress tracking and timer control. It integrates multiple automations and helpers into a single reusable configuration.

## Features
- Automatically updates the charge progress percentage.
- Controls the charger based on a timer and desired charge percentage.
- Ensures the timer duration does not exceed a maximum limit (default: 8 hours 30 minutes).
- Turns off the charger when the timer finishes.

## Inputs

| Input              | Description                                              | Default Value       |
|--------------------|----------------------------------------------------------|---------------------|
| `charger_switch`   | The switch entity controlling the EV Charger charger.        | None (user-defined) |
| `charge_timer`     | The timer entity for the EV Charger charging process.        | None (user-defined) |
| `charge_percentage`| Input number entity for the desired charge percentage.   | None (user-defined) |
| `max_duration`     | Maximum duration for the timer (e.g., `08:30:00`).       | `08:30:00`          |

## Installation

1. Download the `ev_charger_charging_blueprint.yaml` file from this repository.
2. Place the file in your Home Assistant `blueprints/automation` directory.
3. In Home Assistant, navigate to **Settings > Automations & Scenes > Blueprints**.
4. Click **Import Blueprint** and select the file.
5. Configure the blueprint by selecting the required entities and inputs.

## Example Use Case

- **Scenario**: You want to charge your EV Charger to 80% capacity, ensuring the charger turns off automatically when the timer finishes.
- **Setup**:
  - Set the `charger_switch` to your EV Charger charger switch entity.
  - Set the `charge_timer` to your timer entity.
  - Set the `charge_percentage` to an input number entity for the desired charge percentage.
  - Leave the `max_duration` as the default (8 hours 30 minutes) or adjust as needed.

## Notes
- Ensure the entities used in the blueprint are correctly configured in your Home Assistant setup.
- The blueprint is designed to work with a timer that supports `finishes_at` and `duration` attributes.

## Support
If you encounter any issues or have suggestions for improvement, feel free to open an issue in this repository.

