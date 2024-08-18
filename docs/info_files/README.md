# Info File Yaml Formats

Yaml info files are used by drivers to provide information about devices and services to clients.
The information is packed into the standard info structures and passed to the clients. The yaml
format closely matches the format of the info structures.

The following yaml formats are documented:

* [com.robotraconteur.actuator](actuator.md) - `ActuatorInfo`
* [com.robotraconteur.camerainfo](camera.md) - `CameraInfo`, `MultiCameraInfo`, `CameraCalibration`, `PlumbBobDistortionInfo`
* [com.robotraconteur.datetime.clock](clock.md) - `ClockInfo`, `ClockDeviceInfo`
* [com.robotraconteur.color](color.md) - `ColorRGBA`
* [com.robotraconteur.device](device.md) - `DeviceInfo`
* [com.robotraconteur.fiducial](fiducial.md) - `FiducialInfo`, `FiducialSensorInfo`
* [com.robotraconteur.geometry](geometry.md) - `BoundingBox`, `Point`,
  `Pose`, `Quaternion`, `Vector3`, `NamedPose`, `SpatialInertia`
* [com.robotraconteur.identifier](identifier.md) - `Identifier`
* [com.robotraconteur.joystick](joystick.md) - `JoystickInfo`
* [com.robotraconteur.laserscan](laserscan.md) - `LaserScanInfo`
* [com.robotraconteur.laserscanner](laserscanner.md) - `LaserScannerInfo`
* [com.robotraconteur.lighting](lighting.md) - `LightInfo`
* [com.robotraconteur.objectrecognition](objectrecognition.md) - `ObjectRecognitionSensorInfo`
* [com.robotraconteur.pointcloud.sensor](pointcloud.sensor.md) - `PointCloudSensorInfo`
* [com.robotraconteur.robotics.joints](joints.md) - `JointInfo`
* [com.robotraconteur.robotics.payload](payload.md) - `PayloadInfo`
* [com.robotraconteur.robotics.robot](robot.md) - `RobotInfo`, `RobotKinChainInfo`
* [com.robotraconteur.robotics.tool](tool.md) - `ToolInfo
* [com.robotraconteur.sensor](sensor.md) - `SensorInfo`
* [com.robotraconteur.servo](servo.md) - `ServoInfo`
