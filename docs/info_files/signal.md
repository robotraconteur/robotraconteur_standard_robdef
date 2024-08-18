# com.robotraconteur.signal

Info file yaml entries for [com.robotraconteur.signal](../group1/com.robotraconteur.signal.md)

## SignalInfo

The `SignalInfo` structure is used to transmit information about an input/output signal available on a device.

### signal_identifier

Type: [Identifier](identifier.md)

The identifier of the signal. This should match the identifier used by the vendor to identify the signal.
UUID is not required in most cases.

### signal_class

Type: [DeviceClass](device.md#deviceclass)

The type of the signal. The `DeviceClass` structure is used to describe the type of the signal.

### units

Type: `SIUnits`

The units of the signal. The `SIUnits` structure is used to describe the units of the signal.

### data_type

Type: [DataType](datatype.md)

The data type of the signal. The `DataType` structure is used to describe the data type of the signal.

### signal_type

Type: `string`

The type of the signal. See the [SignalType](../group1/com.robotraconteur.signal.md#signaltype) 
enum for possible values. Use the string representation of the enum value.

### access_level

Type: `string`

The access level of the signal. See the [SignalAccessLevel](../group1/com.robotraconteur.signal.md#signalaccesslevel)
enum for possible values. Use the string representation of the enum value.

### address

Type: List&lt;`int`&gt;

The address of the signal. The address is used to identify the signal on the device.

### user_description

Type: `string`

A user-defined description of the signal.

### min_value

Type: `double` or `List<double>`

The minimum value of the signal.

### max_value

Type: `double` or `List<double>`

The maximum value of the signal.

