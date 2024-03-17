# Service: `com.robotraconteur.uuid`

The `com.robotraconteur.uuid` service provides functionality for working with Universally Unique Identifiers (UUIDs).
UUIDs are represented by a byte array containing 128-bits in big-endian order. RFC 4122 defines the standard format
for UUIDs. Gen 4 UUIDs are typically used for new UUIDs.

### Standard Version

The standard version of this service is `0.10`.

## NamedArray: UUID

The `UUID` named array represents a Universally Unique Identifier (UUID) using a byte array.

- `field uint8[16] uuid_bytes`

    The byte array representing the UUID.

This named array allows storing and manipulating UUIDs as a byte array.
