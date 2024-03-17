# Service: `com.robotraconteur.geometryf`

This service is identical to `com.robotraconteur.geometry`, except that all fields are int32 integers
instead of double precision floating point. This service is intended for use with embedded systems
that do not have floating point support, or where floating point support is not desired.

### Standard Version

The standard version of this service is `0.10`.

### Imports

This service imports the following package:

- `com.robotraconteur.identifier`: Includes functionality for working with identifiers.

### Using Statements

This service uses the following statements to import specific types:

- `com.robotraconteur.identifier.Identifier`: Represents an identifier.

### NamedArray: `Vector2`

The `Vector2` named array represents a 2D vector.

- `field int32 x`: The X component of the vector.
- `field int32 y`: The Y component of the vector.

### NamedArray: `Vector3`

The `Vector3` named array represents a 3D vector.

- `field int32 x`: The X component of the vector.
- `field int32 y`: The Y component of the vector.
- `field int32 z`: The Z component of the vector.

### NamedArray: `Vector6`

The `Vector6` named array represents a 6D vector.

- `field int32 alpha`: The alpha component of the vector.
- `field int32 beta`: The beta component of the vector.
- `field int32 gamma`: The gamma component of the vector.
- `field int32 x`: The X component of the vector.
- `field int32 y`: The Y component of the vector.
- `field int32 z`: The Z component of the vector.

### NamedArray: `Point2D`

The `Point2D` named array represents a 2D point.

- `field int32 x`: The X coordinate of the point.
- `field int32 y`: The Y coordinate of the point.

### NamedArray: `Point`

The `Point` named array represents a 3D point.

- `field int32 x`: The X coordinate of the point.
- `field int32 y`: The Y coordinate of the point.
- `field int32 z`: The Z coordinate of the point.

### NamedArray: `Size2D`

The `Size2D` named array represents a 2D size.

- `field int32 width`: The width component of the size.
- `field int32 height`: The height component of the size.

### NamedArray: `Size`

The `Size` named array represents a 3D size.

- `field int32 width`: The width component of the size.
- `field int32 height`: The height component of the size.
- `field int32 depth`: The depth component of the size.

### NamedArray: `Rect`

The `Rect` named array represents a rectangle.

- `field Point2D origin`: The origin point of the rectangle.
- `field Size2D size`: The size of the rectangle.

### NamedArray: `Box`

The `Box` named array represents a 3D box.

- `field Point origin`: The origin point of the box.
- `field Size size`: The size of the box.

### NamedArray: `Quaternion`

The `Quaternion` named array represents a quaternion.

- `field int32 w`: The W component of the quaternion.
- `field int32 x`: The X component of the quaternion.
- `field int32 y`: The Y component of the quaternion.
- `field int32 z`: The Z component of the quaternion.

### NamedArray: `Plane`

The `Plane` named array represents a plane.

- `field Vector3 normal`: The normal vector of the plane.
- `field int32 a`: The distance from the origin to the plane along the normal vector.

### NamedArray: `Transform`

The `Transform` named array represents a transformation in 3D space.

- `field Quaternion rotation`: The rotation component of the transformation.
- `field Vector3 translation`: The translation component of the transformation.

### Struct: `NamedTransform`

The `NamedTransform` structure represents a named transformation between two frames.

- `field Identifier parent_frame`: The parent frame identifier.
- `field Identifier child_frame`: The child frame identifier.
- `field Transform transform`: The transformation between the frames.

### NamedArray: `Pose`

The `Pose` named array represents a pose in 3D space.

- `field Quaternion orientation`: The orientation of the pose.
- `field Point position`: The position of the pose.

### Struct: `NamedPose`

The `NamedPose` structure represents a named pose in 3D space.

- `field Identifier parent_frame`: The parent frame identifier.
- `field Identifier frame`: The frame identifier.
- `field Pose pose`: The pose in the frame.

### Struct: `PoseWithCovariance`

The `PoseWithCovariance` structure represents a pose with covariance in 3D space.

- `field Pose pose`: The pose.
- `field int32[6,6] covariance`: The covariance matrix of the pose.

### Struct: `NamedPoseWithCovariance`

The `NamedPoseWithCovariance` structure represents a named pose with covariance in 3D space.

- `field NamedPose pose`: The named pose.
- `field int32[6,6] covariance`: The covariance matrix of the pose.

### NamedArray: `Pose2D`

The `Pose2D` named array represents a pose in 2D space.

- `field int32 orientation`: The orientation of the pose.
- `field Point2D position`: The position of the pose.

### Struct: `NamedPose2D`

The `NamedPose2D` structure represents a named pose in 2D space.

- `field Identifier parent_frame`: The parent frame identifier.
- `field Identifier frame`: The frame identifier.
- `field Pose2D pose`: The pose in the frame.

### NamedArray: `SpatialVelocity`

The `SpatialVelocity` named array represents a spatial velocity.

- `field Vector3 angular`: The angular velocity.
- `field Vector3 linear`: The linear velocity.

### Struct: `NamedSpatialVelocity`

The `NamedSpatialVelocity` structure represents a named spatial velocity.

- `field Identifier parent_frame`: The parent frame identifier.
- `field Identifier frame`: The frame identifier.
- `field SpatialVelocity velocity`: The spatial velocity in the frame.

### NamedArray: `SpatialAcceleration`

The `SpatialAcceleration` named array represents a spatial acceleration.

- `field Vector3 angular`: The angular acceleration.
- `field Vector3 linear`: The linear acceleration.

### Struct: `NamedSpatialAcceleration`

The `NamedSpatialAcceleration` structure represents a named spatial acceleration.

- `field Identifier parent_frame`: The parent frame identifier.
- `field Identifier frame`: The frame identifier.
- `field SpatialAcceleration acceleration`: The spatial acceleration in the frame.

### NamedArray: `Wrench`

The `Wrench` named array represents a wrench.

- `field Vector3 torque`: The torque component of the wrench.
- `field Vector3 force`: The force component of the wrench.

### Struct: `NamedWrench`

The `NamedWrench` structure represents a named wrench.

- `field Identifier parent_frame`: The parent frame identifier.
- `field Identifier frame`: The frame identifier.
- `field Wrench wrench`: The wrench in the frame.

### NamedArray: `SpatialInertia`

The `SpatialInertia` named array represents a spatial inertia. The spatial inertia is defined in the
frame of the center of mass.

- `field int32 m`: The mass.
- `field Vector3 com`: The center of mass.
- `field int32 ixx`: The moment of inertia about the X-axis.
- `field int32 ixy`: The product of inertia between the X and Y axes.
- `field int32 ixz`: The product of inertia between the X and Z axes.
- `field int32 iyy`: The moment of inertia about the Y-axis.
- `field int32 iyz`: The product of inertia between the Y and Z axes.
- `field int32 izz`: The moment of inertia about the Z-axis.

### Struct: `NamedSpatialInertia`

The `NamedSpatialInertia` structure represents a named spatial inertia.

- `field Identifier frame`: The frame identifier.
- `field SpatialInertia inertia`: The spatial inertia in the frame.

### Struct: `BoundingBox2D`

The `BoundingBox2D` structure represents a 2D bounding box.

- `field NamedPose2D center`: The center pose of the bounding box.
- `field Size2D size`: The size of the bounding box.

### Struct: `BoundingBox`

The `BoundingBox` structure represents a 3D bounding box.

- `field NamedPose center`: The center pose of the bounding box.
- `field Size size`: The size of the bounding box.
