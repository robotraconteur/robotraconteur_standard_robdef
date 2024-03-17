# Service: `com.robotraconteur.resource`

The `com.robotraconteur.resource` service provides functionality for managing and accessing resources stored in buckets.

### Standard Version

The standard version of this service is `0.10`.

### Imports

This service imports the following packages:

- `com.robotraconteur.uuid`: Contains definitions for UUID-related operations.
- `com.robotraconteur.datetime`: Offers functionalities related to date and time.
- `com.robotraconteur.identifier`: Provides definitions for identifiers.

### Using Statements

This service uses the following statements to import specific types:

- `com.robotraconteur.uuid.UUID`: Represents a universally unique identifier (UUID).
- `com.robotraconteur.datetime.DateTimeUTC`: Represents a timestamp in Coordinated Universal Time (UTC).
- `com.robotraconteur.identifier.Identifier`: Represents an identifier.

## Structure: `ResourceIdentifier`

The `ResourceIdentifier` structure represents the identifier of a resource within a bucket.

- `field Identifier bucket`

    The identifier of the bucket that contains the resource.

- `field string key`

    The key that uniquely identifies the resource within the bucket.

## Structure: `BucketInfo`

The `BucketInfo` structure provides information about a bucket.

- `field Identifier identifier`

    The identifier of the bucket.

- `field string{list} keys`

    The list of keys of the resources contained in the bucket.

- `field string description`

    A description of the bucket.

- `field varvalue{string} extended`

    Extended information about the bucket.

## Structure: `ResourceInfo`

The `ResourceInfo` structure provides information about a resource.

- `field ResourceIdentifier identifier`

    The identifier of the resource.

- `field string key`

    The key of the resource within its bucket.

- `field DateTimeUTC created`

    The timestamp indicating when the resource was created.

- `field DateTimeUTC modified`

    The timestamp indicating when the resource was last modified.

- `field uint64 total_size`

    The total size of the resource in bytes.

- `field string description`

    A description of the resource.

- `field varvalue{string} extended`

    Extended information about the resource.

## Structure: `Resource`

The `Resource` structure represents a resource along with its data.

- `field ResourceInfo info`

    Information about the resource.

- `field uint8[] data`

    The data of the resource.

## Structure: `ResourcePart`

The `ResourcePart` structure represents a part of a resource along with its data.

- `field ResourceInfo info`

    Information about the resource part.

- `field uint64 data_offset`

    The offset of the data within the complete resource.

- `field uint8[] data`

    The data of the resource part.

## Object: `ResourceReadOnlyStorage`

The `ResourceReadOnlyStorage` object provides read-only access to resource storage.

### Properties

- `property BucketInfo{list} resource_bucket_info [readonly,nolock]`

    Provides information about the buckets in the resource storage.

### Functions

- `function ResourceInfo resource_get_info(ResourceIdentifier identifier)`

    Retrieves information about a specific resource.
    - `identifier`: The identifier of the resource.
    - Returns: The information about the resource.

- `function ResourcePart{generator} resource_get(ResourceIdentifier identifier)`

    Retrieves a specific resource.
    - `identifier`: The identifier of the resource.
    - Yields: `ResourcePart` objects representing parts of the resource.

- `function ResourcePart{generator} resource_get_all(Identifier bucket_identifier)`

    Retrieves all resources within a bucket.
    - `bucket_identifier`: - `bucket_identifier`: The identifier of the bucket.
    - Yields: `ResourcePart` objects representing parts of the resources within the bucket.

## Object: `ResourceStorage`

The `ResourceStorage` object provides storage and management of resources, including read and write access.

### Implements

- `ResourceReadOnlyStorage`

### Properties

- `property BucketInfo{list} resource_bucket_info [readonly,nolock]`

    Provides information about the buckets in the resource storage.

### Functions

- `function ResourceInfo resource_get_info(ResourceIdentifier identifier)`

    Retrieves information about a specific resource.
    - `identifier`: The identifier of the resource.
    - Returns: The information about the resource.

- `function ResourcePart{generator} resource_get(ResourceIdentifier identifier)`

    Retrieves a specific resource.
    - `identifier`: The identifier of the resource.
    - Yields: `ResourcePart` objects representing parts of the resource.

- `function ResourcePart{generator} resource_get_all(Identifier bucket_identifier)`

    Retrieves all resources within a bucket.
    - `bucket_identifier`: The identifier of the bucket.
    - Yields: `ResourcePart` objects representing parts of the resources within the bucket.

- `function void resource_bucket_add(Identifier bucket_identifier)`

    Adds a new bucket to the resource storage.
    - `bucket_identifier`: The identifier of the new bucket.

- `function void resource_bucket_delete(Identifier bucket_identifier)`

    Deletes a bucket from the resource storage.
    - `bucket_identifier`: The identifier of the bucket to delete.

- `function void resource_set(ResourceIdentifier identifier, bool overwrite, ResourcePart{generator} resource)`

    Sets the data of a resource.
    - `identifier`: The identifier of the resource.
    - `overwrite`: A boolean value indicating whether to overwrite the existing resource.
    - `resource`: A generator yielding `ResourcePart` objects representing parts of the resource.

- `function void resource_delete(ResourceIdentifier identifier)`

    Deletes a resource from the resource storage.
    - `identifier`: The identifier of the resource to delete.

- `function void resource_copy(ResourceIdentifier identifier, ResourceIdentifier new_identifier, bool copy)`

    Copies or moves a resource to a new identifier.
    - `identifier`: The identifier of the resource to copy/move.
    - `new_identifier`: The new identifier for the resource.
    - `copy`: A boolean value indicating whether to copy the resource (`true`) or move it (`false`).
