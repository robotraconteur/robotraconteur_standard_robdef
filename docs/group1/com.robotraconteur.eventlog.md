## Service: `com.robotraconteur.eventlog`

The `com.robotraconteur.eventlog` service is used to manage event logs and log messages.

### Standard Version

The standard version of this service is `0.10`.

### Imports

This service imports the following packages:

- `com.robotraconteur.identifier`: Provides functionality for working with identifiers.
- `com.robotraconteur.datetime`: Offers functionalities related to date and time.
- `com.robotraconteur.device`: Provides functionality for device-related operations.

### Using Statements

This service uses the following statements to import specific types:

- `com.robotraconteur.identifier.Identifier`: Represents a unique identifier.
- `com.robotraconteur.datetime.DateTimeUTC`: Represents a UTC date and time.
- `com.robotraconteur.device.DeviceInfo`: Provides standard device information.
- `com.robotraconteur.device.Device`: Serves as the base interface for devices.

## Enum: `EventLogLevel`

The `EventLogLevel` enum represents the log levels for event logs.

- `undefined` (`0`): Indicates an undefined log level.
- `trace`: Represents a trace log level.
- `debug`: Represents a debug log level.
- `info`: Represents an info log level.
- `warning`: Represents a warning log level.
- `error`: Represents an error log level.
- `safety_violation_error`: Represents a safety violation error log level.
- `fatal_error`: Represents a fatal error log level.
- `emergency_error`: Represents an emergency error log level.
- `catastrophic_error`: Represents a catastrophic error log level.

This enum provides predefined log levels for event logs.

## Structure: `EventLogType`

The `EventLogType` structure represents the type of an event log.

- `field Identifier event_category`

    The category of the event log.

- `field string event_type`

    The type of the event log.

## Structure: `EventLogMessageHeader`

The `EventLogMessageHeader` structure represents the header of an event log message.

- `field EventLogType type`

    The type of the event log.

- `field EventLogLevel level`

    The log level of the event log.

- `field Identifier source_device`

    The identifier of the source device.

- `field string source_component`

    The component associated with the event log.

- `field string source_object`

    The object associated with the event log.

- `field uint64 message_number`

    The message number of the event log.

- `field DateTimeUTC timestamp`

    The timestamp of the event log.

## Structure: `EventLogMessage`

The `EventLogMessage` structure represents an event log message.

- `field EventLogMessageHeader header`

    The header of the event log message.

- `field string title`

    The title of the event log message.

- `field string message`

    The content of the event log message.

- `field varvalue{string} extended`

    Extended information about the event log message.

## Structure: `EventLogInfo`

The `EventLogInfo` structure provides information about an event log.

- `field DeviceInfo device_info`

    Provides standard device information such as the name, model, and serial number.

- `field Identifier logged_device`

    The identifier of the device being logged.

- `field uint64 min_message_number`

    The minimum message number of the event log.

- `field uint64 max_message_number`

    The maximum message number of the event log.

- `field varvalue{string} extended`

    Extended information about the event log.

## Object: `EventLog`

### Properties

- `property EventLogInfo eventlog_info [readonly,nolock]`

    Provides information about the event log.

### Functions

- `function EventLogMessage{list} getf_eventlog_messages(uint64 start, uint64 count)`

    Retrieves a list of event log messages within the specified range.
    - `start`: The starting message number.
    - `count`: The number of messages to retrieve.
    - Returns: A list of event log messages.

## Object: `EventLogDevice`

### Implements

- `EventLog`
- `Device`

### Properties

- `property DeviceInfo device_info [readonly,nolock]`

    Provides standard device information such as the name, model, and serial number.

- `property EventLogInfo eventlog_info [readonly,nolock]`

    Provides information about the event log.

### Functions

- `function EventLogMessage{list} getf_eventlog_messages(uint64 start, uint64 count)`

    Retrieves a list of event log messages within the specified range.
    - `start`: The starting message number.
    - `count`: The number of messages to retrieve.
    - Returns: A list of event log messages.

- `pipe EventLogMessage eventlog_message_stream [readonly]`

    A read-only pipe for streaming event log messages.

- `function void eventlog_clear_messages(uint64 offset, uint64 count)`

    Clears event log messages within the specified range.
    - `offset`: The starting message number.
    - `count`: The number of messages to clear.

- `function void eventlog_clear_all_messages()`

    Clears all event log messages.

