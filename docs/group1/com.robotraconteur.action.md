# Service: `com.robotraconteur.action`

This service provides functionality for managing long-running operations using generators. The generators typically return a structure with an `action_status` field of type `ActionStatusCode`.

## Standard Version

The standard version of this service is `0.10`.

## Enum: `ActionStatusCode`

The `ActionStatusCode` enum represents the status of an action.

- `error` (`-3`): Indicates that an error occurred during the execution of the action.
- `failed` (`-2`): Indicates that the action failed to execute successfully.
- `cancelled` (`-1`): Indicates that the action was cancelled before it could complete.
- `unknown` (`0`): Indicates that the status of the action is unknown.
- `queued` (implicitly `1`): Indicates that the action has been queued for execution but has not yet started.
- `running` (implicitly `2`): Indicates that the action is currently running.
- `complete` (implicitly `3`): Indicates that the action has completed successfully.

This enum is commonly used in the context of long-running operations to track the progress and outcome of an action.

