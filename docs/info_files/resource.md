# com.robotraconteur.resource

Info file yaml entries for [com.robotraconteur.resource](../group1/com.robotraconteur.resource.md)

## ResourceIdentifier

Resources are often provided by devices that are too large to return as part of info structures.
Resources are used instead, with a separate service delivering the resource data. The `ResourceIdentifier`
structure is used to identify the resource so that the data can be retrieved.

### bucket

Type: [Identifier](identifier.md)

The identifier of the bucket that contains the resource. The client will need to search available
resource storage services to find the bucket that contains the resource.

### key

Type: `string`

The key that uniquely identifies the resource within the bucket.

