# Home Assistant Blueprint: Ventilation Recommendation by Absolute Humidity

Home Assistant blueprint that calculates absolute humidity ($g/m^3$) from temperature and relative humidity for both indoor and outdoor sensors, determining whether ventilation is recommended.

## Features

- **Graphical Wizard / UI Selectors**:
  - Indoor temperature sensor (`device_class: temperature`)
  - Indoor relative humidity sensor (`device_class: humidity`)
  - Outdoor temperature sensor (`device_class: temperature`)
  - Outdoor relative humidity sensor (`device_class: humidity`)
  - Configurable minimum humidity difference threshold ($g/m^3$)
  - Minimum indoor temperature guard
- **Output Options**:
  - Sets an `input_boolean` helper (`true` / `false` for "Lüften empfohlen")
  - Optional `input_number` helpers to store calculated indoor and outdoor absolute humidity values ($g/m^3$)
  - Custom actions on ventilation recommended (e.g. notifications, lights) and not recommended

## Calculation Formula

Absolute humidity ($AH$ in $g/m^3$) is calculated using the Magnus-Tetens approximation:

$$AH = \frac{6.112 \cdot e^{\frac{17.67 \cdot T}{T + 243.5}} \cdot \frac{RH}{100} \cdot 216.7}{273.15 + T}$$

## License

MIT - Copyright (c) Eidolf
