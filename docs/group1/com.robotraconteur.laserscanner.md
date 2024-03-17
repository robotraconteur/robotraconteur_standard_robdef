# Service: `com.robotraconteur.laserscanner`

The `com.robotraconteur.laserscanner` service is used to represent laser scanners and provides functionality for acquiring laser scan data.

### Standard Version

The standard version of this service is `0.10`.

### Imports

This service imports the following packages:

- `com.robotraconteur.device`: Provides functionality for device-related operations.
- `com.robotraconteur.param`: Includes definitions for parameter-related information.
- `com.robotraconteur.laserscan`: Contains definitions related to laser scan data.

### Using Statements

This service uses the following statements to import specific types:

- `com.robotraconteur.device.DeviceInfo`: Represents information about the device associated with the laser scanner.
- `com.robotraconteur.device.Device`: Serves as the base interface for devices.
- `com.robotraconteur.param.ParameterInfo`: Provides information about the parameters associated with the laser scanner.
- `com.robotraconteur.laserscan.LaserScanInfof as LaserScanInfo`: Represents information about a laser scan.
- `com.robotraconteur.laserscan.LaserScanf as LaserScan`: Represents a full laser scan.
- `com.robotraconteur.laserscan.LaserScanPartf as LaserScanPart`: Represents a part of a laser scan.

## Structure: `LaserScannerInfo`

The `LaserScannerInfo` structure is used to provide information about a laser scanner. It is returned by the `scanner_info`
property of the `LaserScanner` object.

- `field DeviceInfo device_info`

    Provides standard device information such as the name, model, and serial number.

- `field LaserScanInfo scanner_info`

    Provides information about the laser scanner.

- `field double scan_rate`

    The scan rate of the laser scanner.

- `field ParameterInfo{list} param_info`

    Provides information about the parameters of the laser scanner. Used with the `getf_param` and `setf_param` functions.

- `field varvalue{string} extended`

    Extended information about the laser scanner.

## Object: `LaserScanner`

### Implements

- `Device`

### Properties

- `property DeviceInfo device_info [readonly,nolock]`

    Provides standard device information such as the name, model, and serial number.

- `property LaserScannerInfo scanner_info [readonly,nolock]`

    Provides information about the laser scanner.

### Pipes

- `pipe LaserScan laser_scan_sensor_data [readonly]`

    A continuous stream of laser scan data produced by the laser scanner.

### Functions

- `function varvalue getf_param(string param_name)`

    Get the value of a parameter.
    - `param_name`: The name of the parameter to get.
    - Returns: The value of the parameter.

- `function void setf_param(string param_name, varvalue value)`

    Set the value of a parameter.
    - `param_name`: The name of the parameter to set.
    - `value`: The value to set the parameter to.

## Object: `LaserScanPartScanner`

### Properties

- `property LaserScannerInfo scanner_info [readonly,nolock]`

    Provides information about the laser scanner.

### Pipes

- `pipe LaserScanPart laser_scan_sensor_data [readonly]`

    A continuous stream of partial laser scan data produced by the laser scanner.

### Functions

- `function varvalue getf_param(string param_name)`

    Get the value of a parameter.
    - `param_name`: The name of the parameter to get.
    - Returns: The value of the parameter.

- `function void setf_param(string param_name, varvalue value)`

    Set the value of a parameter.
    - `param_name`: The name of the parameter to set.
    - `value`: The value to set the parameter to.

This object represents a laser scanner that provides partial laser scan data.
