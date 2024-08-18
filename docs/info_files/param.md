# com.robotraconteur.param

Info file yaml entries for [com.robotraconteur.param](../group1/com.robotraconteur.param.md)

## ParameterInfo

The `ParameterInfo` structure is used to transmit information about a parameter available on a device.
These parameters are modified using the `getf_param` and `setf_param` functions of the device.

### parameter_identifier

Type: [Identifier](identifier.md)

The identifier of the parameter.

### parameter_class

Type: [DeviceClass](device.md#deviceclass)

The class of the parameter.

### data_type

Type: [DataType](datatype.md)

The data type of the parameter value.

### data_units

Type: `SIUnits`

The units of measurement for the parameter value.

### description

Type: `string`

The description of the parameter.

### default_value

Type: `double` or `List<double>`

The default value of the parameter.

### min_value

Type: `double` or `List<double>`

The minimum allowed value for the parameter.

### max_value

Type: `double` or `List<double>`

The maximum allowed value for the parameter.

### enum_values

Type: `List<string>`

The possible values for the parameter if it is an enumerated type.

### extended

Type: Map&lt;string,[Extended](extended.md)&gt;

Extended information.