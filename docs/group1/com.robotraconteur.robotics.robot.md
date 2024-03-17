# Service: `com.robotraconteur.robotics.robot`

The `com.robotraconteur.robotics.robot` service represents a robot and provides functionalities related to robot control and monitoring.

### Standard Version

The standard version of this service is `0.10`.

### Imports

This service imports the following packages:

- `com.robotraconteur.geometry`: Provides geometric types and operations.
- `com.robotraconteur.sensordata`: Includes definitions for sensor data.
- `com.robotraconteur.device`: Provides functionality for device-related operations.
- `com.robotraconteur.signal`: Defines signal-related information.
- `com.robotraconteur.param`: Includes definitions for parameter-related information.
- `com.robotraconteur.robotics.joints`: Contains definitions for robotic joints.
- `com.robotraconteur.robotics.tool`: Provides information about robotic tools.
- `com.robotraconteur.robotics.payload`: Contains definitions for robotic payloads.
- `com.robotraconteur.robotics.trajectory`: Defines trajectory-related information.
- `com.robotraconteur.identifier`: Contains definitions for identifiers.
- `com.robotraconteur.action`: Provides functionality for robotic actions.
- `com.robotraconteur.eventlog`: Defines event log-related information.
- `com.robotraconteur.device.isoch`: Contains definitions for isochronous devices.
- `com.robotraconteur.device.clock`: Provides functionality for device clocks.
- `com.robotraconteur.datetime`: Offers functionalities related to date and time.
- `com.robotraconteur.fiducial`: Provides information about fiducials.

### Using Statements

This service uses the following statements to import specific types:

- `com.robotraconteur.geometry.Point`: Represents a point in 3D space.
- `com.robotraconteur.geometry.Vector3`: Represents a 3D vector.
- `com.robotraconteur.geometry.Transform`: Represents a transformation in 3D space.
- `com.robotraconteur.geometry.SpatialInertia`: Represents spatial inertia.
- `com.robotraconteur.geometry.Pose`: Represents a pose in 3D space.
- `com.robotraconteur.geometry.SpatialVelocity`: Represents spatial velocity.
- `com.robotraconteur.geometry.SpatialAcceleration`: Represents spatial acceleration.
- `com.robotraconteur.sensordata.SensorDataHeader`: Represents the header information of sensor data.
- `com.robotraconteur.device.DeviceInfo`: Represents information about the device associated with the robot.
- `com.robotraconteur.device.Device`: Serves as the base interface for devices.
- `com.robotraconteur.signal.SignalInfo`: Provides information about a signal.
- `com.robotraconteur.robotics.joints.JointInfo`: Represents information about a robotic joint.
- `com.robotraconteur.robotics.tool.ToolInfo`: Represents information about a robotic tool.
- `com.robotraconteur.robotics.payload.PayloadInfo`: Represents information about a robotic payload.
- `com.robotraconteur.param.ParameterInfo`: Provides information about a parameter.
- `com.robotraconteur.robotics.trajectory.TrajectoryStatus`: Represents the status of a trajectory.
- `com.robotraconteur.robotics.trajectory.JointTrajectory`: Represents a trajectory defined by joint positions.
- `com.robotraconteur.robotics.trajectory.InterpolationMode`: Represents the interpolation mode for trajectory execution.
- `com.robotraconteur.identifier.Identifier`: Represents an identifier.
- `com.robotraconteur.action.ActionStatusCode`: Represents the status code of an action.
- `com.robotraconteur.eventlog.EventLogMessage` : Represents an event log message.
- `com.robotraconteur.device.isoch.IsochDevice`: Provides functionality for isochronous devices.
- `com.robotraconteur.device.isoch.IsochInfo`: Represents information about an isochronous device.
- `com.robotraconteur.device.clock.DeviceClock`: Represents a device clock.
- `com.robotraconteur.device.clock.DeviceTime`: Represents device time.
- `com.robotraconteur.datetime.TimeSpec3`: Represents a timestamp with nanosecond precision.
- `com.robotraconteur.fiducial.Fiducial`: Represents information about a fiducial.

## Enum: `RobotTypeCode`

The `RobotTypeCode` enum represents the types of robots that can be used within the `com.robotraconteur.robotics.robot` service.

- `unknown` (`0`): Represents an unknown robot type.
- `serial` (`1`): Represents a serial robot.
- `dual_arm`: Represents a robot with two arms.
- `differential_drive`: Represents a robot with a differential drive.
- `planar`: Represents a planar robot.
- `floating`: Represents a floating robot.
- `freeform`: Represents a freeform robot.
- `other`: Represents a robot with a type not listed in this enum.

This enum provides a set of predefined robot types. If the robot type is not listed in this enum, use `unknown` and provide additional information in the `DeviceInfo` structure.

## Enum: `RobotCommandMode`

The `RobotCommandMode` enum represents the command modes of a robot within the `com.robotraconteur.robotics.robot` service.

- `invalid_state` (`-1`): Indicates an invalid state of the robot.
- `halt` (`0`): Indicates a halted state of the robot.
- `jog`: Indicates a jog command mode.
- `trajectory`: Indicates a trajectory command mode.
- `position_command`: Indicates a position command mode.
- `velocity_command`: Indicates a velocity command mode.
- `homing`: Indicates a homing command mode.

## Enum: `RobotOperationalMode`

The `RobotOperationalMode` enum represents the operational modes of a robot within the `com.robotraconteur.robotics.robot` service.

- `undefined` (`0`): Represents an undefined operational mode.
- `manual_reduced_speed`: Represents a manual mode with reduced speed.
- `manual_full_speed`: Represents a manual mode with full speed.
- `auto`: Represents an automatic mode.
- `cobot`: Represents a collaborative robot (cobot) mode.

## Enum: `RobotControllerState`

The `RobotControllerState` enum represents the states of the controller of a robot within the `com.robotraconteur.robotics.robot` service.

- `undefined` (`0`): Represents an undefined state of the controller.
- `init` (`1`): Represents the initialization state of the controller.
- `motor_on`: Represents the motor-on state of the controller.
- `motor_off`: Represents the motor-off state of the controller.
- `guard_stop`: Represents a guard stop condition of the controller.
- `emergency_stop`: Represents an emergency stop condition of the controller.
- `emergency_stop_reset`: Represents a reset of the emergency stop condition of the controller.

## Enum: `RobotCapabilities`

The `RobotCapabilities` enum represents the capabilities supported by a robot within the `com.robotraconteur.robotics.robot` service.

- `unknown` (`0`): Represents unknown capabilities.
- `jog_command` (`0x1`): Indicates support for jog commands.
- `trajectory_command` (`0x2`): Indicates support for trajectory commands.
- `position_command` (`0x4`): Indicates support for position commands.
- `velocity_command` (`0x8`): Indicates support for velocity commands.
- `homing_command` (`0x10`): Indicates support for homing commands.
- `software_reset_errors` (`0x20`): Indicates support for software resetting of errors.
- `software_enable` (`0x40`): Indicates support for software enabling of the robot.
- `interpolated_trajectory` (`0x80`): Indicates support for interpolated trajectories.
- `raster_trajectory` (`0x100`): Indicates support for raster trajectories.
- `trajectory_queueing` (`0x200`): Indicates support for trajectory queueing.
- `speed_ratio` (`0x400`): Indicates support for adjusting the speed ratio of the robot.

This enum provides a set of capabilities that can be supported by a robot. Each capability is represented by a flag that can be combined using bitwise OR.

## Enum: `RobotStateFlags`

The `RobotStateFlags` enum represents the state flags of a robot. These flags are used to indicate various states and conditions of the robot.

- `unknown` (`0`): Represents an unknown state of the robot.
- `error` (`0x1`): Indicates an error condition of the robot.
- `fatal_error` (`0x2`): Indicates a fatal error condition of the robot.
- `estop` (`0x4`): Indicates an emergency stop condition of the robot.
- `estop_button1` (`0x8`): Indicates the state of emergency stop button 1.
- `estop_button2` (`0x10`): Indicates the state of emergency stop button 2.
- `estop_button3` (`0x20`): Indicates the state of emergency stop button 3.
- `estop_button4` (`0x40`): Indicates the state of emergency stop button 4.
- `estop_guard1` (`0x80`): Indicates the state of emergency stop guard 1.
- `estop_guard2` (`0x100`): Indicates the state of emergency stop guard 2.
- `estop_guard3` (`0x200`): Indicates the state of emergency stop guard 3.
- `estop_guard4` (`0x400`): Indicates the state of emergency stop guard 4.
- `estop_software` (`0x800`): Indicates a software emergency stop condition of the robot.
- `estop_fault` (`0x1000`): Indicates a fault emergency stop condition of the robot.
- `estop_internal` (`0x2000`): Indicates an internal emergency stop condition of the robot.
- `estop_other` (`0x4000`): Indicates another type of emergency stop condition of the robot.
- `estop_released` (`0x8000`): Indicates that the emergency stop condition has been released.
- `enabling_switch` (`0x10000`): Indicates the state of the enabling switch of the robot.
- `enabled` (`0x20000`): Indicates that the robot is enabled.
- `ready` (`0x40000`): Indicates that the robot is ready for operation.
- `homed` (`0x80000`): Indicates that the robot has been homed.
- `homing_required` (`0x100000`): Indicates that homing is required for the robot.
- `communication_failure` (`0x200000`): Indicates a communication failure with the robot.
- `valid_position_command` (`0x1000000`): Indicates that a valid position command has been sent to the robot.
- `valid_velocity_command` (`0x2000000`): Indicates that a valid velocity command has been sent to the robot.
- `trajectory_running` (`0x4000000`): Indicates that a trajectory is currently running on the robot.

These flags provide information about the state and conditions of the robot. Each flag represents a specific state or condition and can be combined using bitwise OR.

## Structure: `RobotKinChainInfo`

The `RobotKinChainInfo` structure provides information about a kinematic chain of a robot within the `com.robotraconteur.robotics.robot` service.

- `field Identifier kin_chain_identifier`

    The identifier of the kinematic chain.

- `field Vector3[] H`

    The H vectors of the kinematic chain.

- `field Vector3[] P`

    The P vectors of the kinematic chain.

- `field SpatialInertia[] link_inertias`

    The inertias of the links in the kinematic chain.

- `field Identifier{list} link_identifiers`

    The identifiers of the links in the kinematic chain.

- `field Fiducial{list} link_fiducials`

    The fiducials associated with the links in the kinematic chain.

- `field uint32[] joint_numbers`

    The joint numbers in the kinematic chain.

- `field Pose flange_pose`

    The pose of the flange in the kinematic chain.

- `field Identifier flange_identifier`

    The identifier of the flange.

- `field ToolInfo current_tool`

    Information about the current tool attached to the kinematic chain.

- `field PayloadInfo current_payload`

    Information about the current payload attached to the kinematic chain.

- `field SpatialVelocity tcp_max_velocity`

    The maximum velocity of the tool center point (TCP) in the kinematic chain.

- `field SpatialAcceleration tcp_max_acceleration`

    The maximum acceleration of the tool center point (TCP) in the kinematic chain.

- `field SpatialVelocity tcp_reduced_max_velocity`

    The maximum reduced velocity of the tool center point (TCP) in the kinematic chain.

- `field SpatialAcceleration tcp_reduced_max_acceleration`

    The maximum reduced acceleration of the tool center point (TCP) in the kinematic chain.

- `field string description`

    A description of the kinematic chain.

- `field varvalue{string} extended`

    Extended information about the kinematic chain.

This structure provides detailed information about a kinematic chain in a robot, including link properties, joint numbers, flange pose, current tool and payload, TCP velocities and accelerations, and additional descriptive and extended information.

## Structure: `RobotInfo`

The `RobotInfo` structure provides information about a robot within the `com.robotraconteur.robotics.robot` service.

- `field DeviceInfo device_info`

    Provides standard device information such as the name, model, and serial number of the robot.

- `field RobotTypeCode robot_type`

    The type of the robot.

- `field JointInfo{list} joint_info`

    Information about the joints of the robot.

- `field RobotKinChainInfo{list} chains`

    Information about the kinematic chains of the robot.

- `field uint32 robot_capabilities`

    The capabilities supported by the robot.

- `field SignalInfo{list} signal_info`

    Information about the signals associated with the robot.

- `field ParameterInfo{list} parameter_info`

    Information about the parameters of the robot.

- `field uint16 config_seqno`

    The configuration sequence number of the robot.

- `field InterpolationMode{list} trajectory_interpolation_modes`

    The supported interpolation modes for trajectory execution.

- `field varvalue{string} extended`

    Extended information about the robot.

This structure provides comprehensive information about a robot, including its device information, type, joint information, kinematic chain information, capabilities, signal information, parameter information, configuration sequence number, supported trajectory interpolation modes, and additional extended information.

## Structure: `RobotState`

The `RobotState` structure represents the state of a robot within the `com.robotraconteur.robotics.robot` service.

- `field TimeSpec3 ts`

    The timestamp of the robot state.

- `field uint64 seqno`

    The sequence number of the robot state.

- `field RobotCommandMode command_mode`

    The command mode of the robot.

- `field RobotOperationalMode operational_mode`

    The operational mode of the robot.

- `field RobotControllerState controller_state`

    The state of the robot controller.

- `field uint64 robot_state_flags`

    The state flags of the robot.

- `field double[] joint_position`

    The current joint positions of the robot.

- `field double[] joint_velocity`

    The current joint velocities of the robot.

- `field double[] joint_effort`

    The current joint efforts of the robot.

- `field double[] joint_position_command`

    The commanded joint positions of the robot.

- `field double[] joint_velocity_command`

    The commanded joint velocities of the robot.

- `field Pose[] kin_chain_tcp`

    The TCP poses of the kinematic chains in the robot.

- `field SpatialVelocity[] kin_chain_tcp_vel`

    The TCP velocities of the kinematic chains in the robot.

- `field bool trajectory_running`

    Indicates whether a trajectory is currently running on the robot.

This structure provides the current state of a robot, including the timestamp, sequence number, command mode, operational mode, controller state, state flags, joint positions, joint velocities, joint efforts, commanded joint positions and velocities, TCP poses, TCP velocities, and the status of a running trajectory.

## Structure: `AdvancedRobotState`

The `AdvancedRobotState` structure represents an advanced state of a robot within the `com.robotraconteur.robotics.robot` service.

- `field TimeSpec3 ts`

    The timestamp of the advanced robot state.

- `field uint64 seqno`

    The sequence number of the advanced robot state.

- `field RobotCommandMode command_mode`

    The command mode of the robot.

- `field RobotOperationalMode operational_mode`

    The operational mode of the robot.

- `field RobotControllerState controller_state`

    The state of the robot controller.

- `field uint64 robot_state_flags`

    The state flags of the robot.

- `field double[] joint_position`

    The current joint positions of the robot.

- `field double[] joint_velocity`

    The current joint velocities of the robot.

- `field double[] joint_effort`

    The current joint efforts of the robot.

- `field double[] joint_position_command`

    The commanded joint positions of the robot.

- `field double[] joint_velocity_command`

    The commanded joint velocities of the robot.

- `field uint8[] joint_position_units`

    The units of the joint positions.

- `field uint8[] joint_effort_units`

    The units of the joint efforts.

- `field Pose[] kin_chain_tcp`

    The TCP poses of the kinematic chains in the robot.

- `field SpatialVelocity[] kin_chain_tcp_vel`

    The TCP velocities of the kinematic chains in the robot.

- `field bool trajectory_running`

    Indicates whether a trajectory is currently running on the robot.

- `field double trajectory_time`

    The current time within the running trajectory.

- `field double trajectory_max_time`

    The maximum time of the running trajectory.

- `field uint32 trajectory_current_waypoint`

    The index of the current waypoint in the running trajectory.

- `field uint16 config_seqno`

    The configuration sequence number of the robot.

This structure provides an advanced state of a robot, including the timestamp, sequence number, command mode, operational mode, controller state, state flags, joint positions, joint velocities, joint efforts, commanded joint positions and velocities, joint position units, joint effort units, TCP poses, TCP velocities, the status of a running trajectory, trajectory time, maximum trajectory time, current waypoint index, and configuration sequence number.

## Structure: `RobotStateSensorData`

The `RobotStateSensorData` structure represents sensor data associated with the robot state within the `com.robotraconteur.robotics.robot` service.

- `field SensorDataHeader data_header`

    The header information of the sensor data.

- `field AdvancedRobotState robot_state`

    The advanced state of the robot.

This structure combines the sensor data header with the advanced robot state, providing a complete package of sensor data associated with the robot state.

## Structure: `RobotJointCommand`

The `RobotJointCommand` structure represents a joint command for the robot within the `com.robotraconteur.robotics.robot` service.

- `field uint64 seqno`

    The sequence number of the joint command.

- `field uint64 state_seqno`

    The sequence number of the robot state at which the command was generated.

- `field double[] command`

    The joint command values.

- `field uint8[] units`

    The units of the joint command values. (Using `JointUnits` values)

This structure encapsulates a joint command, including the sequence number, state sequence number, joint command values, and the units associated with the command.

## Object: Robot

The `Robot` object implements several interfaces and provides properties, functions, wires, and events to control and monitor the robot.

### Implements

- Device: The `Robot` object implements the `Device` interface, which provides standard device-related functionality.
- DeviceClock: The `Robot` object implements the `DeviceClock` interface, allowing synchronization with a device clock.
- IsochDevice: The `Robot` object implements the `IsochDevice` interface, providing isochronous data transfer capabilities.

### Properties

- `property DeviceInfo device_info [readonly, nolock]`

    Provides standard device information such as the name, model, and serial number.

- `property RobotInfo robot_info [readonly, nolock]`

    Provides information about the robot.

- `property RobotCommandMode command_mode [nolockread]`

    Gets or sets the command mode of the robot.

- `property RobotOperationalMode operational_mode [readonly, nolock]`

    Gets the operational mode of the robot.

- `property RobotControllerState controller_state [readonly, nolock]`

    Gets the state of the robot's controller.

- `property EventLogMessage{list} current_errors [readonly, nolock]`

    Gets the current error messages associated with the robot.

- `property double speed_ratio`

    Gets or sets the speed ratio of the robot.

- `property IsochInfo isoch_info [readonly, nolock]`

    Provides information about isochronous data transfer.

- `property uint32 isoch_downsample [perclient]`

    Specifies the downsample value for isochronous data transfer.

### Functions

- `function void halt() [urgent]`

    Halts the robot's motion immediately.

- `function void enable()`

    Enables the robot for operation.

- `function void disable() [urgent]`

    Disables the robot and prevents further operation.

- `function void reset_errors()`

    Resets the robot's error state.

- `function void jog_freespace(double[] joint_position, double[] max_velocity, bool wait)`

    Jogs the robot's joints in free space to the specified joint positions.
    - `joint_position`: The target joint positions.
    - `max_velocity`: The maximum joint velocities allowed during the jog.
    - `wait`: Specifies whether to wait until the jog is complete before returning.

- `function void jog_joint(double[] joint_velocity, double timeout, bool wait)`

    Jogs the robot's joints at the specified joint velocities.
    - `joint_velocity`: The target joint velocities.
    - `timeout`: The maximum time allowed for the jog.
    - `wait`: Specifies whether to wait until the jog is complete before returning.

- `function void jog_cartesian(SpatialVelocity{int32} max_velocity, double timeout, bool wait)`

    Jogs the robot's end-effector in Cartesian space at the specified maximum velocities.
    - `max_velocity`: The maximum Cartesian velocities allowed during the jog.
    - `timeout`: The maximum time allowed for the jog.
    - `wait`: Specifies whether to wait until the jog is complete before returning.

- `function TrajectoryStatus{generator} execute_trajectory(JointTrajectory trajectory)`

    Executes a joint trajectory on the robot.
    - `trajectory`: The joint trajectory to execute.
    - Returns: A generator that provides the trajectory execution status.

- `function ActionStatusCode{generator} home()`

    Homes the robot, returning the status of the home operation.
    - Returns: A generator that provides the status of the home operation.

- `function double[] getf_signal(string signal_name)`

    Gets the value of a signal associated with the robot.
    - `signal_name`: The name of the signal to get.
    - Returns

- `setf_signal(string signal_name, double[] value)`

    Sets the value of a signal associated with the robot.
    - `signal_name`: The name of the signal to set.
    - `value`: The value to set the signal to.

- `function void tool_attached(int32 chain, ToolInfo tool)`

    Attaches a tool to the specified chain of the robot.
    - `chain`: The chain to which the tool will be attached.
    - `tool`: Information about the tool being attached.

- `function void tool_detached(int32 chain, string tool_name)`

    Detaches the tool with the specified name from the specified chain of the robot.
    - `chain`: The chain from which the tool will be detached.
    - `tool_name`: The name of the tool to detach.

- `function void payload_attached(int32 chain, PayloadInfo payload, Pose pose)`

    Attaches a payload to the specified chain of the robot.
    - `chain`: The chain to which the payload will be attached.
    - `payload`: Information about the payload being attached.
    - `pose`: The pose of the payload relative to the robot.

- `function void payload_detached(int32 chain, string payload_name)`

    Detaches the payload with the specified name from the specified chain of the robot.
    - `chain`: The chain from which the payload will be detached.
    - `payload_name`: The name of the payload to detach.

- `function varvalue getf_param(string param_name)`

    Gets the value of a parameter associated with the robot.
    - `param_name`: The name of the parameter to get.
    - Returns: The value of the parameter.

- `function void setf_param(string param_name, varvalue value)`

    Sets the value of a parameter associated with the robot.
    - `param_name`: The name of the parameter to set.
    - `value`: The value to set the parameter to.

### Wires

- `wire RobotState robot_state [readonly, nolock]`

    Represents the state of the robot as a `RobotState` structure.

- `wire AdvancedRobotState advanced_robot_state [readonly, nolock]`

    Represents the advanced state of the robot as an `AdvancedRobotState` structure.

- `wire DeviceTime device_clock_now [readonly, nolock]`

    Represents the current device time.

- `wire RobotJointCommand position_command [writeonly]`

    Sends joint position commands to the robot.

- `wire RobotJointCommand velocity_command [writeonly]`

    Sends joint velocity commands to the robot.

### Pipes

- `pipe RobotStateSensorData robot_state_sensor_data [readonly, nolock]`

    Provides sensor data related to the robot's state.

### Events

- `event tool_changed(int32 chain, string tool_name)`

    Triggered when a tool attached to a chain of the robot changes.

- `event payload_changed(int32 chain, string payload_name)`

    Triggered when a payload attached to a chain of the robot changes.

- `event param_changed(string param_name)`

    Triggered when a parameter associated with the robot changes.

The `Robot` object represents a robot with various capabilities. It provides properties to access information about the robot, such as its device info, robot info, command mode, operational mode, and controller state. The object also allows enabling, disabling, and halting the robot
