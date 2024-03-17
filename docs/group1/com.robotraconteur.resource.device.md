# Service: `com.robotraconteur.resource.device`

The `com.robotraconteur.resource.device` service combines the functionality of the `com.robotraconteur.device` and `com.robotraconteur.resource` services to provide device-related operations with resource storage capabilities.

### Standard Version

The standard version of this service is `0.10`.

### Imports

This service imports the following packages:

- `com.robotraconteur.device`: Provides functionality for device-related operations.
- `com.robotraconteur.resource`: Offers functionalities for managing and accessing resources.
- `com.robotraconteur.identifier`: Provides definitions for identifiers.

### Using Statements

This service uses the following statements to import specific types:

- `com.robotraconteur.identifier.Identifier`: Represents an identifier.
- `com.robotraconteur.device.Device`: Serves as the base interface for devices.
- `com.robotraconteur.device.DeviceInfo`: Represents information about the device associated with the resource storage.
- `com.robotraconteur.resource.BucketInfo`: Provides information about a resource storage bucket.
- `com.robotraconteur.resource.ResourceIdentifier`: Represents the identifier of a resource.
- `com.robotraconteur.resource.ResourcePart`: Represents a part of a resource.
- `com.robotraconteur.resource.ResourceInfo`: Provides information about a resource.
- `com.robotraconteur.resource.ResourceReadOnlyStorage`: Provides read-only access to resource storage.
- `com.robotraconteur.resource.ResourceStorage`: Provides storage and management of resources.

## Object: `ResourceStorageDevice`

The `ResourceStorageDevice` object implements the `Device`, `ResourceReadOnlyStorage`, and `ResourceStorage` interfaces, combining device-related operations with resource storage capabilities.

### Implements

- `Device`
- `ResourceReadOnlyStorage`
- `ResourceStorage`

### Properties

- `property DeviceInfo device_info [readonly,nolock]`

    Provides standard device information such as the name, model, and serial number.

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
