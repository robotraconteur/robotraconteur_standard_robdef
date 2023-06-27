## Service: `com.robotraconteur.laserscan`

The `com.robotraconteur.laserscan` service provides functionality for working with laser scan data.

### Standard Version

The standard version of this service is `0.10`.

### Imports

This service imports the following packages:

- `com.robotraconteur.image`: Provides functionality for working with images.
- `com.robotraconteur.sensordata`: Contains definitions for sensor data.

### Using Statements

This service uses the following statements to import specific types:

- `com.robotraconteur.image.PixelRGB`: Represents an RGB pixel.
- `com.robotraconteur.sensordata.SensorDataHeader`: Contains header information for sensor data.

## Structure: `LaserScanInfo`

The `LaserScanInfo` structure represents information about a laser scan.

- `field SensorDataHeader data_header`

    The header information of the laser scan data.

- `field double angle_min`

    The minimum angle of the laser scan.

- `field double angle_max`

    The maximum angle of the laser scan.

- `field double angle_increment`

    The angle increment between consecutive measurements.

- `field uint32 angle_count`

    The number of measurements in the horizontal direction.

- `field double vertical_angle_min`

    The minimum vertical angle of the laser scan.

- `field double vertical_angle_max`

    The maximum vertical angle of the laser scan.

- `field double vertical_angle_increment`

    The vertical angle increment between consecutive measurements.

- `field uint32 vertical_angle_count`

    The number of measurements in the vertical direction.

- `field double time_increment`

    The time increment between consecutive measurements.

- `field double scan_time`

    The total time it took to perform the laser scan.

- `field double range_min`

    The minimum range value of the laser scan.

- `field double range_max`

    The maximum range value of the laser scan.

- `field double range_resolution`

    The resolution of the range measurements.

## Structure: `LaserScan`

The `LaserScan` structure represents a complete laser scan.

- `field LaserScanInfo scan_info`

    The information about the laser scan.

- `field double[] ranges`

    The range measurements of the laser scan.

- `field double[] intensities`

    The intensity measurements associated with the range measurements.

- `field PixelRGB[] color`

    The color values associated with the range measurements.

- `field int32[] fiducial`

    The fiducial values associated with the range measurements.

- `field varvalue{string} extended`

    Additional extended information about the laser scan.

## Structure: `LaserScanInfof`

The `LaserScanInfof` structure represents information about a laser scan using single-precision floating-point values.

- `field SensorDataHeader data_header`

    The header information of the laser scan data.

- `field single angle_min`

    The minimum angle of the laser scan.

- `field single angle_max`

    The maximum angle of the laser scan.

- `field single angle_increment`

    The angle increment between consecutive measurements.

- `field uint32 angle_count`

    The number of measurements in the horizontal direction.

- `field single vertical_angle_min`

    The minimum vertical angle of the laser scan.

- `field single vertical_angle_max`

    The maximum vertical angle of the laser scan.

- `field single vertical_angle_increment`

    The vertical angle increment between consecutive measurements.

- `field uint32 vertical_angle_count`

    The number of measurements in the vertical direction.

- `field single time_increment`

    The time increment between consecutive measurements.

- `field single scan_time`

    The total time it took to perform the laser scan.

- `field single range_min`

    The minimum range value of the laser scan.

- `field single range_max`

    The maximum range value of the laser scan.

- `field single range_resolution`

    The resolution of the range measurements.

## Structure: `LaserScanf`

The `LaserScanf` structure represents a complete laser scan using single-precision floating-point values.

- `field LaserScanInfof scan_info`

    The information about the laser scan.

- `field single[] ranges`

    The range measurements of the laser scan.

- `field single[] intensities`

    The intensity measurements associated with the range measurements.

- `field PixelRGB[] color`

    The color values associated with the range measurements.

- `field int32[] fiducial`

    The fiducial values associated with the range measurements.

- `field varvalue{string} extended`

    Additional extended information about the laser scan.

## Structure: `LaserScanPart`

The `LaserScanPart` structure represents a part of a laser scan.

- `field LaserScanInfo scan_info`

    The information about the laser scan.

- `field uint32 data_offset`

    The offset of the data part within the complete laser scan.

- `field uint32 data_total_len`

    The total length of the complete laser scan.

- `field double[] ranges`

    The range measurements of the laser scan part.

- `field double[] intensities`

    The intensity measurements associated with the range measurements.

- `field PixelRGB[] color`

    The color values associated with the range measurements.

- `field int32[] fiducial`

    The fiducial values associated with the range measurements.

- `field varvalue{string} extended`

    Additional extended information about the laser scan part.

## Structure: `LaserScanPartf`

The `LaserScanPartf` structure represents a part of a laser scan using single-precision floating-point values.

- `field LaserScanInfof scan_info`

    The information about the laser scan.

- `field uint32 data_offset`

    The offset of the data part within the complete laser scan.

- `field uint32 data_total_len`

    The total length of the complete laser scan.

- `field single[] ranges`

    The range measurements of the laser scan part.

- `field single[] intensities`

    The intensity measurements associated with the range measurements.

- `field PixelRGB[] color`

    The color values associated with the range measurements.

- `field int32[] fiducial`

    The fiducial values associated with the range measurements.

- `field varvalue{string} extended`

    Additional extended information about the laser scan part.
