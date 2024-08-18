# com.robotraconteur.robotics.joints

Info file yaml entries for [com.robotraconteur.robotics.joints](../group1/com.robotraconteur.robotics.joints.md)

## JointInfo

The `JointInfo` structure is used to transmit information about a joint in a kinematic chain. 

### joint_identifior

Type: [Identifier](identifier.md)

The identifier of the joint. The identifier is typically only a string. Many uses such as planners, simulators,
and controllers depend on the joint name. Be careful when defining the joint name that it is
consistent with the rest of the system.

### joint_type

Type `string`

The type of the joint. See the [JointTypeCode](../group1/com.robotraconteur.robotics.joints.md#enum-jointtypecode) enum
for a list of standard joint types. Use the string representation of the enum value. Default is `revolute`.

### joint_limits

Type: [JointLimits](#jointlimits)

The limits of the joint.

### default_units

Type: `string`

The default units of the joint. If not specified, the default units are radians for revolute joints and meters 
for prismatic joints. See the [JointUnitsCode](../group1/com.robotraconteur.robotics.joints.md#enum-jointunitscode) enum.
Use the string representation of the enum value.

### default_effort_units

Type: `string`

The default effort units of the joint. If not specified, the default effort units are newton-meters for revolute joints
and newtons for prismatic joints. 
See the [JointEffortUnitsCode](../group1/com.robotraconteur.robotics.joints.md#enum-jointeffortunitscode) enum.
Use the string representation of the enum value.

### passive

Type: `bool`

Indicates whether the joint is passive or not. Default is `false`.

### extended

Type: Map&lt;string,[Extended](extended.md)&gt;

Extended information.

## JointLimits

The `JointLimits` structure is used to define the limits and constraints associated with a joint.

### lower

Type: `double`

The lower limit of the joint.

### upper

Type: `double`

The upper limit of the joint.

### home

Type: `double`

The home position of the joint. Default is 0.

### velocity

Type: `double`

The maximum velocity of the joint.

### acceleration

Type: `double`

The maximum acceleration of the joint.

### jerk

Type: `double`

The maximum jerk of the joint.

### effort

Type: `double`

The maximum effort (torque, force, etc) of the joint.

### reduced_velocity

Type: `double`

The reduced maximum velocity of the joint. Default is the same as `velocity`. 
This field is used when the joint is in a reduced velocity mode such as jogging.

### reduced_acceleration

Type: `double`

The reduced maximum acceleration of the joint. Default is the same as `acceleration`.
This field is used when the joint is in a reduced velocity mode such as jogging.

### reduced_jerk

Type: `double`

The reduced maximum jerk of the joint. Default is the same as `jerk`.
This field is used when the joint is in a reduced velocity mode such as jogging.
