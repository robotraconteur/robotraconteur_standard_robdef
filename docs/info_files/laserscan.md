# com.robotraconteur.laserscan

Info file yaml entries for [com.robotraconteur.laserscan](../group1/com.robotraconteur.laserscan.md)

## LaserScanInfo

The `LaserScanInfo` structure is used to transmit information about the format of a laser scan.

### angle_min

Type: `double`

The minimum angle of the laser scan in radians.

### angle_max

Type: `double`

The maximum angle of the laser scan in radians.

### angle_increment

Type: `double`

The angle increment between consecutive measurements in radians.

### angle_count

Type: `int`

The number of measurements in the horizontal direction.

### vertical_angle_min

Type: `double`

The minimum vertical angle of the laser scan in radians.

### vertical_angle_max

Type: `double`

The maximum vertical angle of the laser scan in radians.

### vertical_angle_increment

Type: `double`

The vertical angle increment between consecutive measurements in radians.

### vertical_angle_count

Type: `int`

The number of measurements in the vertical direction.

### time_increment

Type: `double`

The time increment between consecutive measurements in seconds.

### scan_time

Type: `double`

The total time it takes to perform the laser scan in seconds.

### range_min

Type: `double`

The minimum range value of the laser scan in meters.

### range_max

Type: `double`

The maximum range value of the laser scan in meters.

### range_resolution

Type: `double`

The resolution of the range measurements in meters.
