# Service: `com.robotraconteur.units`

The `com.robotraconteur.units` service provides functionality for handling units of measurement. The
exact format of the units is not specified, but the service provides a standard structure for representing
units.

### Standard Version

The standard version of this service is `0.10`.

## Structure: SIUnit

The `SIUnit` structure represents a measurement unit using the International System of Units (SI).

- `field string display_units`

    The display units for the measurement unit.

- `field string encoded_units`

    The encoded units for the measurement unit.

This structure allows specifying the display and encoded units for a measurement unit.
