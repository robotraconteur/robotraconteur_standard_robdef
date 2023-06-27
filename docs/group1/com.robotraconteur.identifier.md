## Service: `com.robotraconteur.identifier`

The `com.robotraconteur.identifier` service provides functionality for representing identifiers with names and 
universally unique identifiers (UUIDs).

The UUID is typically used to uniquely identify the identifier, while the name is used to provide a human-readable
name for the identifier. A UUID of all zeros is considered to be "any", and an empty name is considered to be "any".

Identifiers have complex matching rules:

- If both identifiers are "any", they match
- If either identifier is "any", they match
- If both identifiers have the same name and UUID, they match
- If the name is Any for either identifier and UUID matches, they match
- If the UUID is Any for either identifier and name matches, they match
- Otherwise, they do not match

### Standard Version

The standard version of this service is `0.10`.

### Imports

This service imports the following package:

- `com.robotraconteur.uuid`: Represents universally unique identifiers (UUIDs).

### Using Statements

This service uses the following statement to import specific types:

- `com.robotraconteur.uuid.UUID`: Represents a universally unique identifier.

## Structure: `Identifier`

The `Identifier` structure represents an identifier with a name and a UUID within the `com.robotraconteur.identifier` service.

- `field string name`

    The name of the identifier.

- `field UUID uuid`

    The universally unique identifier (UUID) associated with the identifier.

