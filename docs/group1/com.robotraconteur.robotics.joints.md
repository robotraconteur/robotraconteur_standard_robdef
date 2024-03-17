# Service: `com.robotraconteur.robotics.joints`

The `com.robotraconteur.robotics.joints` service provides definitions and information related to robotic joints.

### Standard Version

The standard version of this service is `0.10`.

### Imports

This service imports the following package:

- `com.robotraconteur.units`: Defines units of measurement.
- `com.robotraconteur.identifier`: Provides definitions for identifiers.

### Using Statements

This service uses the following statements to import specific types:

- `com.robotraconteur.units.SIUnit`: Represents a measurement unit using the International System of Units (SI).
- `com.robotraconteur.identifier.Identifier`: Represents an identifier.

## Enum: `JointPositionUnits`

The `JointPositionUnits` enum represents the units of measurement for joint positions.

- `implicit` (`0`): Indicates that the unit is implicit or not specified.
- `meter`: Represents the unit of meters.
- `radian`: Represents the unit of radians.
- `degree`: Represents the unit of degrees.
- `ticks_lin`: Represents the unit of linear ticks (m/(2^20)).
- `ticks_rot`: Represents the unit of rotational ticks (rev/(2^20)).
- `nanoticks_lin`: Represents the unit of linear nanoticks (nm/(2^20)).
- `nanoticks_rot`: Represents the unit of rotational nanoticks (nrev/(2^20)).

This enum provides various units for specifying joint positions. The `implicit` value indicates that the unit is not explicitly specified.

## Enum: `JointVelocityUnits`

The `JointVelocityUnits` enum represents the units of measurement for joint velocities.

- `implicit` (`0`): Indicates that the unit is implicit or not specified.
- `meter_second` (`16`): Represents the unit of meters per second.
- `radian_second`: Represents the unit of radians per second.
- `degree_second`: Represents the unit of degrees per second.
- `ticks_lin_second`: Represents the unit of linear ticks per second.
- `ticks_rot_second`: Represents the unit of rotational ticks per second.
- `nanoticks_lin_second`: Represents the unit of linear nanoticks per second.
- `nanoticks_rot_second`: Represents the unit of rotational nanoticks per second.

This enum provides various units for specifying joint velocities. The `implicit` value indicates that the unit is not explicitly specified.

## Enum: `JointAccelerationUnits`

The `JointAccelerationUnits` enum represents the units of measurement for joint accelerations.

- `implicit` (`0`): Indicates that the unit is implicit or not specified.
- `meter_second2` (`32`): Represents the unit of meters per second squared.
- `radian_second2`: Represents the unit of radians per second squared.
- `degree_second2`: Represents the unit of degrees per second squared.
- `ticks_lin_second2`: Represents the unit of linear ticks per second squared.
- `ticks_rot_second2`: Represents the unit of rotational ticks per second squared.
- `nanoticks_lin_second2`: Represents the unit of linear nanoticks per second squared.
- `nanoticks_rot_second2`: Represents the unit of rotational nanoticks per second squared.

This enum provides various units for specifying joint accelerations. The `implicit` value indicates that the unit is not explicitly specified.

## Enum: `JointJerkUnits`

The `JointJerkUnits` enum represents the units of measurement for joint jerks.

- `implicit` (`0`): Indicates that the unit is implicit or not specified.
- `meter_second2` (`48`): Represents the unit of meters per second cubed.
- `radian_second3`: Represents the unit of radians per second cubed.
- `degree_second3`: Represents the unit of degrees per second cubed.
- `ticks_lin_second3`: Represents the unit of linear ticks per second cubed.
- `ticks_rot_second3`: Represents the unit of rotational ticks per second cubed.
- `nanoticks_lin_second3`: Represents the unit of linear nanoticks per second cubed.
- `nanoticks_rot_second3`: Represents the unit of rotational nanoticks per second cubed.

This enum provides various units for specifying joint jerks. The `implicit` value indicates that the unit is not explicitly specified.

## Enum: `JointEffortUnits`

The `JointEffortUnits` enum represents the units of measurement for joint efforts.

- `implicit` (`0`): Indicates that the unit is implicit or not specified.
- `newton` (`64`): Represents the unit of Newtons.
- `newton_meter`: Represents the unit of Newton-meters.
- `ampere`: Represents the unit of Amperes.
- `volt`: Represents the unit of Volts.
- `pascal`: Represents the unit of Pascals.
- `coulomb`: Represents the unit of Coulombs.
- `tesla`: Represents the unit of Teslas.
- `weber`: Represents the unit of Webers.
- `meter_second2`: Represents the unit of meters per second squared.
- `radian_second2`: Represents the unit of radians per second squared.
- `degree_second2`: Represents the unit of degrees per second squared.

This enum provides various units for specifying joint efforts. The `implicit` value indicates that the unit is not explicitly specified.

## Enum: `JointType`

The `JointType` enum represents the type of a robotic joint.

- `unknown` (`0`): Represents an unknown joint type.
- `revolute`: Represents a revolute joint.
- `continuous`: Represents a continuous joint.
- `prismatic`: Represents a prismatic joint.
- `wheel`: Represents a wheel joint.
- `screw`: Represents a screw joint.
- `other`: Represents another type of joint.
- `revolute2`: Represents a compound joint type of two revolute joints.
- `universal`: Represents a compound joint type of a universal joint.
- `ball`: Represents a compound joint type of a ball joint.
- `planar`: Represents a compound joint type of a planar joint.
- `floating`: Represents a compound joint type of a floating joint.
- `other_compound`: Represents another type of compound joint.
- `fixed`: Represents a fixed joint used in scenes.

This enum provides a set of predefined joint types. If the joint type is not listed in this enum, use `unknown` and provide additional details in the `JointInfo` structure.

## Structure: `JointLimits`

The `JointLimits` structure represents the limits of a robotic joint.

- `field double lower`

    The lower limit of the joint position.

- `field double upper`

    The upper limit of the joint position.

- `field double home`

    The home position of the joint.

- `field double velocity`

    The maximum velocity of the joint.

- `field double acceleration`

    The maximum acceleration of the joint.

- `field double jerk`

    The maximum jerk of the joint.

- `field double effort`

    The maximum effort (torque) of the joint.

- `field double reduced_velocity`

    The reduced maximum velocity of the joint.

- `field double reduced_acceleration`

    The reduced maximum acceleration of the joint.

- `field double reduced_jerk`

    The reduced maximum jerk of the joint.

- `field double reduced_effort`

    The reduced maximum effort (torque or force) of the joint.

This structure defines the limits and constraints associated with a robotic joint.

## Structure: `JointInfo`

The `JointInfo` structure provides information about a robotic joint.

- `field Identifier joint_identifier`

    The identifier of the joint.

- `field JointType joint_type`

    The type of the joint.

- `field JointLimits joint_limits`

    The limits and constraints of the joint.

- `field JointPositionUnits default_units`

    The default units of measurement for joint positions.

- `field JointEffortUnits default_effort_units`

    The default units of measurement for joint efforts.

- `field bool passive`

    Indicates whether the joint is passive or not.

- `field varvalue{string} extended`

    Extended information about the joint.
