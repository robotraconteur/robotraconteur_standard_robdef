## Service: `com.robotraconteur.octree`

The `com.robotraconteur.octree` service is used to represent octree data.

### Standard Version

The standard version of this service is `0.10`.

### Imports

This service imports the following packages:

- `com.robotraconteur.sensordata`: Contains definitions for sensor data.
- `com.robotraconteur.identifier`: Provides functionality for object identification.
- `com.robotraconteur.resource`: Represents a resource identifier.

### Using Statements

This service uses the following statements to import specific types:

- `com.robotraconteur.sensordata.SensorDataHeader`: Represents the header information of sensor data.
- `com.robotraconteur.identifier.Identifier`: Represents an identifier for an object.
- `com.robotraconteur.resource.ResourceIdentifier`: Represents a resource identifier.

## Enum: `OcTreeEncoding`

The `OcTreeEncoding` enum represents different encodings used for octree data.

- `unknown` (`0`): Indicates an unknown encoding.
- `octomap_ot`: Indicates the encoding used by OctoMap in occupancy octree format.
- `octomap_bt`: Indicates the encoding used by OctoMap in binary octree format.
- `other`: Indicates another encoding format.

This enum provides a set of predefined octree encodings.

## Structure: `OcTreeInfo`

The `OcTreeInfo` structure provides information about an octree. It includes the sensor data header, encoding, identifier, and resolution of the octree.

- `field SensorDataHeader data_header`

    The header information of the octree sensor data.

- `field OcTreeEncoding encoding`

    The encoding format of the octree.

- `field string id`

    The identifier of the octree.

- `field double resolution`

    The resolution of the octree.

## Structure: `OcTree`

The `OcTree` structure represents an octree. It contains the octree information and the octree data.

- `field OcTreeInfo octree_info`

    The information about the octree.

- `field uint8[] data`

    The octree data stored as a byte array.

- `field varvalue{string} extended`

    Extended information about the octree.

## Structure: `OcTreePart`

The `OcTreePart` structure represents a part of an octree. It contains partial octree information and the octree data corresponding to the part.

- `field OcTreeInfo octree_info`

    The information about the octree part.

- `field uint32 data_offset`

    The offset of the octree data within the complete octree.

- `field uint32 data_total_len`

    The total length of the octree data within the complete octree.

- `field uint8[] data`

    The octree data corresponding to the part stored as a byte array.

- `field varvalue{string} extended`

    Extended information about the octree part.

## Structure: `OcTreeResource`

The `OcTreeResource` structure represents an octree resource. It contains the identifier of the octree resource.

- `field ResourceIdentifier octree_resource`

    The identifier of the octree resource. The resource can be retrieved from a 
    `com.robotraconteur.resource.ResourceStorage` service.

