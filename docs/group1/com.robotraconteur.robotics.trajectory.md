# Service: `com.robotraconteur.robotics.trajectory`

The `com.robotraconteur.robotics.trajectory` service provides functionality for defining and executing trajectories in robotics applications.

### Standard Version

The standard version of this service is `0.10`.

### Imports

This service imports the following packages:

- `com.robotraconteur.robotics.joints`: Defines joint-related functionalities.
- `com.robotraconteur.identifier`: Provides functionality for identifiers.
- `com.robotraconteur.action`: Offers functionalities for actions.

### Using Statements

This service uses the following statements to import specific types:

- `com.robotraconteur.robotics.joints.JointPositionUnits`: Represents units of joint positions.
- `com.robotraconteur.robotics.joints.JointEffortUnits`: Represents units of joint efforts.
- `com.robotraconteur.identifier.Identifier`: Represents an identifier.
- `com.robotraconteur.action.ActionStatusCode`: Represents the status code of an action.

## Enum: `InterpolationMode`

The `InterpolationMode` enum represents the interpolation modes for trajectory waypoints in the `com.robotraconteur.robotics.trajectory` service.

- `default` (`0`): Represents the default interpolation mode.
- `joint`: Represents joint interpolation mode.
- `linear`: Represents linear interpolation mode.
- `cylindrical`: Represents cylindrical interpolation mode.
- `spherical`: Represents spherical interpolation mode.
- `joint_cubic_spline`: Represents joint cubic spline interpolation mode.
- `cubic_spline`: Represents cubic spline interpolation mode.
- `custom`: Represents a custom interpolation mode.

This enum provides a set of predefined interpolation modes for trajectory waypoints.

## Enum: `TrajectoryWaypointType`

The `TrajectoryWaypointType` enum represents the types of trajectory waypoints in the `com.robotraconteur.robotics.trajectory` service.

- `unspecified` (`0`): Represents an unspecified waypoint type.
- `start` (`1`): Represents the start waypoint of a trajectory.
- `path`: Represents a path waypoint.
- `goal`: Represents a goal waypoint.
- `intermediate_stop`: Represents an intermediate stop waypoint.
- `raster`: Represents a raster waypoint.
- `other`: Represents another type of waypoint.

This enum provides a set of predefined waypoint types for trajectories.

## Structure: `JointTrajectoryWaypoint`

The `JointTrajectoryWaypoint` structure represents a waypoint in a joint trajectory. It is used in the `JointTrajectory` structure.

- `field double[] joint_position`

    The joint positions for the waypoint.

- `field double[] joint_velocity`

    The joint velocities for the waypoint.

- `field double[] position_tolerance`

    The position tolerances for each joint.

- `field double[] velocity_tolerance`

    The velocity tolerances for each joint.

- `field InterpolationMode interpolation_mode`

    The interpolation mode for the waypoint.

- `field TrajectoryWaypointType waypoint_type`

    The type of the waypoint.

- `field double time_from_start`

    The time from the start of the trajectory to the waypoint.

This structure represents a waypoint in a joint trajectory, including joint positions, velocities, tolerances, interpolation mode, waypoint type, and time information.

## Structure: `JointTrajectory`

The `JointTrajectory` structure represents a joint trajectory in the `com.robotraconteur.robotics.trajectory` service.

- `field string{list} joint_names`

    The names of the joints in the trajectory.

- `field JointPositionUnits{list} joint_units`

    The units of joint positions for each joint.

- `

field JointTrajectoryWaypoint{list} waypoints`

    The waypoints in the trajectory.

- `field varvalue{string} extended`

    Extended information about the trajectory.

This structure represents a joint trajectory, including joint names, units, waypoints, and extended information.

## Structure: `TrajectoryStatus`

The `TrajectoryStatus` structure represents the status of a trajectory in the `com.robotraconteur.robotics.trajectory` service.

- `field uint64 seqno`

    The sequence number of the trajectory status.

- `field ActionStatusCode action_status`

    The status code of the trajectory action.

- `field uint32 current_waypoint`

    The index of the current waypoint in the trajectory.

- `field double trajectory_time`

    The current time in the trajectory.

This structure represents the status of a trajectory, including sequence number, action status, current waypoint index, and trajectory time.

## Structure: `AdvancedJointTrajectoryDeviceWaypoint`

The `AdvancedJointTrajectoryDeviceWaypoint` structure represents a waypoint for an advanced joint trajectory device. It is used in the `AdvancedJointTrajectoryWaypoint` structure.

- `field double[]{list} joint_position`

    The joint positions for the waypoint.

- `field double[]{list} joint_velocity`

    The joint velocities for the waypoint.

- `field double[]{list} joint_acceleration`

    The joint accelerations for the waypoint.

- `field double[]{list} joint_jerk`

    The joint jerks for the waypoint.

- `field double[]{list} joint_effort`

    The joint efforts for the waypoint.

- `field double[]{list} position_tolerance`

    The position tolerances for each joint.

- `field double[]{list} velocity_tolerance`

    The velocity tolerances for each joint.

- `field InterpolationMode interpolation_mode`

    The interpolation mode for the waypoint.

- `field TrajectoryWaypointType waypoint_type`

    The type of the waypoint.

- `field varvalue{string} signals`

    Additional signals associated with the waypoint.

This structure represents a waypoint for an advanced joint trajectory device, including joint positions, velocities, accelerations, jerks, efforts, tolerances, interpolation mode, waypoint type, and additional signals.

## Structure: `AdvancedJointTrajectoryWaypoint`

The `AdvancedJointTrajectoryWaypoint` structure represents a waypoint in an advanced joint trajectory. It is used in the `AdvancedJointTrajectory` structure.

- `field AdvancedJointTrajectoryDeviceWaypoint{list} joints`

    The joint waypoints for the advanced joint trajectory.

- `field double time_from_start`

    The time from the start of the trajectory to the waypoint.

This structure represents a waypoint in an advanced joint trajectory, including joint waypoints and time information.

## Structure: `AdvancedJointTrajectoryDevice`

The `AdvancedJointTrajectoryDevice` structure represents an advanced joint trajectory device in the `com.robotraconteur.robotics.trajectory` service.

- `field Identifier device`

    The identifier of the device.

- `field string{list} joint_names`

    The names of the joints in the device.

- `field JointPositionUnits{list} joint_units`

    The units of joint positions for each joint.

- `field JointEffortUnits{list} joint_effort_units`

    The units of joint efforts for each joint.

- `field varvalue{string} extended`

    Extended information about the device.

This structure represents an advanced joint trajectory device, including the device identifier, joint names, joint units, joint effort units, and extended information.

## Structure: `AdvancedJointTrajectory`

The `AdvancedJointTrajectory` structure represents an advanced joint trajectory in the `com.robotraconteur.robotics.trajectory` service.

- `field

 AdvancedJointTrajectoryDevice{list} devices`

    The devices participating in the trajectory.

- `field AdvancedJointTrajectoryWaypoint{list} waypoints`

    The waypoints in the trajectory.

- `field varvalue{string} extended`

    Extended information about the trajectory.

This structure represents an advanced joint trajectory, including the participating devices, waypoints, and extended information.

## Structure: `FreeformJointTrajectoryWaypoint`

The `FreeformJointTrajectoryWaypoint` structure represents a waypoint in a freeform joint trajectory. It is used in the `FreeformJointTrajectory` structure.

- `field varvalue{list} joint_position`

    The joint positions for the waypoint.

- `field varvalue{list} joint_velocity`

    The joint velocities for the waypoint.

- `field varvalue{list} position_tolerance`

    The position tolerances for each joint.

- `field varvalue{list} velocity_tolerance`

    The velocity tolerances for each joint.

- `field string interpolation_mode`

    The interpolation mode for the waypoint.

- `field varvalue{string} signals`

    Additional signals associated with the waypoint.

- `field double time_from_start`

    The time from the start of the trajectory to the waypoint.

- `field varvalue{string} extended`

    Extended information about the waypoint.

This structure represents a waypoint in a freeform joint trajectory, including joint positions, velocities, tolerances, interpolation mode, signals, time information, and extended information.

## Structure: `FreeformJointTrajectory`

The `FreeformJointTrajectory` structure represents a freeform joint trajectory in the `com.robotraconteur.robotics.trajectory` service.

- `field string{list} joint_names`

    The names of the joints in the trajectory.

- `field string{list} joint_units`

    The units of joint positions for each joint.

- `field FreeformJointTrajectoryWaypoint{list} waypoints`

    The waypoints in the trajectory.

- `field varvalue{string} extended`

    Extended information about the trajectory.

This structure represents a freeform joint trajectory, including joint names, units, waypoints, and extended information.
