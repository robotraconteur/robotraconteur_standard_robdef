# Service: `com.robotraconteur.param`

The `com.robotraconteur.param` service is used to represent parameter information. It is typically
used to represent the parameters available for use with `getf_param` and `setf_param` functions.

### Standard Version

The standard version of this service is `0.10`.

### Imports

This service imports the following packages:

- `com.robotraconteur.identifier`: Provides functionality for object identification.
- `com.robotraconteur.datatype`: Contains data type definitions.
- `com.robotraconteur.device`: Provides functionality for device-related operations.
- `com.robotraconteur.units`: Defines units of measurement.

### Using Statements

This service uses the following statements to import specific types:

- `com.robotraconteur.identifier.Identifier`: Represents an identifier for an object.
- `com.robotraconteur.datatype.DataType`: Defines the data type used for parameter values.
- `com.robotraconteur.device.DeviceClass`: Represents the class of a device.
- `com.robotraconteur.units.SIUnit`: Represents a measurement unit using the International System of Units (SI).

## Structure: `ParameterInfo`

The `ParameterInfo` structure provides information about a parameter. It includes the parameter identifier, class, data type, data units, description, default value, minimum value, maximum value, enum values, and extended information.

- `field Identifier parameter_identifier`

    The identifier of the parameter.

- `field DeviceClass parameter_class`

    The class of the parameter.

- `field DataType data_type`

    The data type of the parameter value.

- `field SIUnit{list} data_units`

    The units of measurement for the parameter value. These are typically SI units.

- `field string description`

    The description of the parameter.

- `field varvalue default_value`

    The default value of the parameter.

- `field varvalue min_value`

    The minimum allowed value for the parameter.

- `field varvalue max_value`

    The maximum allowed value for the parameter.

- `field varvalue{string} enum_values`

    The allowed values for the parameter if it is an enumerated type.

- `field varvalue{string} extended`

    Extended information about the parameter.
