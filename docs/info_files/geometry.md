# com.robotraconteur.geometry

Info file yaml entries for [com.robotraconteur.geometry](../group1/com.robotraconteur.geometry.md)

Most structures and namedarray types in the geometry robdef can be used in info files.

## Quaternion

The `Quaternion` structure represents a quaternion in a coordinate system.

### w

Type: `double`

The w component of the quaternion.

### x

Type: `double`

The x component of the quaternion.

### y

Type: `double`

The y component of the quaternion.

### z

Type: `double`

The z component of the quaternion.

## Point

The `Point` structure represents a point in a coordinate system. All units are in meters.

### x

Type: `double`

The x component of the point.

### y

Type: `double`

The y component of the point.

### z

Type: `double`

The z component of the point.

## Pose

The `Pose` structure represents a pose in a coordinate system.

### orientation

Type: [Quaternion](#quaternion)

The orientation of the pose.

### position

Type: [Point](#point)

The position of the pose.

## NamedPose

The `NamedPose` structure represents a named pose in a coordinate system.

### parent_frame

Type: [Indentifier](identifier.md)

The identifier of the parent frame. May be omitted if not used.

### frame

Type: [Indentifier](identifier.md)

The identifier of the frame. May be omitted if not used.

### pose

Type: [Pose](#pose)

The pose of the frame in the parent frame.

### Vector3

The `Vector3` structure represents a three component vector. Use MKS units if applicable.

### x

Type: `double`

The x component of the vector.

### y

Type: `double`

The y component of the vector.

### z

Type: `double`

The z component of the vector.

## SpatialVelocity

The `SpatialVelocity` structure represents a spatial velocity in a coordinate system. This includes
both linear and angular velocity.

### angular

Type: [Vector3](#vector3)

The angular velocity in radians per second.

### linear

Type: [Vector3](#vector3)

The linear velocity in meters per second.

## SpatialAcceleration

The `SpatialAcceleration` structure represents a spatial acceleration in a coordinate system. This includes
both linear and angular acceleration.

### angular

Type: [Vector3](#vector3)

The angular acceleration in radians per second squared.

### linear

Type: [Vector3](#vector3)

The linear acceleration in meters per second squared.

## SpatialInertia

The `SpatialInertia` structure represents the mass properties if an object. It is defined
in the coordinate system of the link. The `com` field is the vector from the origin of the
link to the center of mass. The inertia tensor is defined about the center of mass.

### m

Type: `double`

The mass of the object in kilograms.

### com

Type: [Vector3](#vector3)

The location of center of mass of the object in meters relative to the link origin.

### ixx

Type: `double`

The ixx component of the inertia tensor in kg m^2.

### ixy

Type: `double`

The ixy component of the inertia tensor in kg m^2.

### ixz

Type: `double`

The ixz component of the inertia tensor in kg m^2.

### iyy

Type: `double`

The iyy component of the inertia tensor in kg m^2.

### iyz

Type: `double`

The iyz component of the inertia tensor in kg m^2.

### izz

Type: `double`

The izz component of the inertia tensor in kg m^2.

## Size2D

The `Size2D` structure represents a two dimensional size.

### width

Type: `double`

The width of the size. Use meters if applicable.

### height

Type: `double`

The height of the size. Use meters if applicable.

## Transform

The `Transform` structure represents a translation and rotation transformation matrix.

### rotation

Type: [Quaternion](#quaternion)

The rotation component of the transformation.

### translation

Type: [Vector3](#vector3)

The translation component of the transformation.
