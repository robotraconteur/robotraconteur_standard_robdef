# Service: `com.robotraconteur.pointcloud`

The `com.robotraconteur.pointcloud` service provides structures for representing point cloud data and defines various point cloud-related types.

### Standard Version

The standard version of this service is `0.10`.

### Imports

This service imports the following packages:

- `com.robotraconteur.geometry`: Contains definitions for geometric objects.
- `com.robotraconteur.geometryf`: Contains definitions for geometric objects with single-precision floating-point values.
- `com.robotraconteur.image`: Provides functionality for working with images.

### Using Statements

This service uses the following statements to import specific types:

- `com.robotraconteur.geometry.Point`: Represents a point in three-dimensional space.
- `com.robotraconteur.geometry.Vector3`: Represents a vector in three-dimensional space.
- `com.robotraconteur.geometry.BoundingBox`: Represents a bounding box that encloses a region in three-dimensional space.
- `com.robotraconteur.geometryf.Point`: Represents a point in three-dimensional space with single-precision floating-point values.
- `com.robotraconteur.geometryf.Vector3`: Represents a vector in three-dimensional space with single-precision floating-point values.
- `com.robotraconteur.geometryf.BoundingBox`: Represents a bounding box that encloses a region in three-dimensional space with single-precision floating-point values.
- `com.robotraconteur.image.PixelRGBFloatPacked`: Represents a pixel with red, green, and blue color channels stored as floating-point values.
- `com.robotraconteur.image.PixelRGBFloatPackedf`: Represents a pixel with red, green, and blue color channels stored as single-precision floating-point values.

## Structure: `PointCloud`

The `PointCloud` structure represents a point cloud. It includes information about the bounding box, density, and an array of points.

- `field BoundingBox bounds`

    The bounding box that encloses the point cloud.

- `field bool is_dense`

    A flag indicating whether the point cloud is dense.

- `field Point[] points`

    An array of points in the point cloud.

- `field varvalue{string} extended`

    Extended information about the point cloud.

## Structure: `PointCloudPart`

The `PointCloudPart` structure represents a part of a point cloud. It includes information about the bounding box, density, offset, total length, and an array of points corresponding to the part.

- `field BoundingBox bounds`

    The bounding box that encloses the point cloud part.

- `field bool is_dense`

    A flag indicating whether the point cloud part is dense.

- `field uint32 points_offset`

    The offset of the points within the complete point cloud.

- `field uint32 points_total_len`

    The total length of the points within the complete point cloud.

- `field Point[] points`

    An array of points corresponding to the part of the point cloud.

- `field varvalue{string} extended`

    Extended information about the point cloud part.

## Structure: `PointCloudf`

The `PointCloudf` structure represents a point cloud with single-precision floating-point values. It includes information about the bounding box, density, and an array of points.

- `field BoundingBoxf bounds`

    The bounding box that encloses the point cloud.

- `field bool is_dense`

    A flag indicating whether the point cloud is dense.

- `field Pointf[] points`

    An array of points in the point cloud.

- `field varvalue{string} extended`

    Extended information about the point cloud.

## Structure: `PointCloudPartf`

The `PointCloudPartf` structure represents a part of a point cloud with single-precision floating-point values. It includes information about the bounding box, density, offset, total length, and an array of points corresponding to the part.

- `field BoundingBoxf bounds`

    The bounding box that encloses the point cloud part.

- `field bool is_dense`

    A flag indicating whether the point cloud part is dense.

- `field uint32 points_offset`

    The offset of the points within the complete point cloud.

- `field uint32 points_total_len`

    The total length of the points within the complete point cloud.

- `field Pointf[] points`

    An array of points corresponding to the part of the point cloud.

- `field varvalue{string} extended`

    Extended information about the point cloud part.

## Structure: `PointCloud2`

The `PointCloud2` structure represents a point cloud with additional attributes such as intensity, normal, RGB color, moment invariants, and channel. It includes information about the bounding box, density, and an array of points.

- `field BoundingBox bounds`

    The bounding box that encloses the point cloud.

- `field bool is_dense`

    A flag indicating whether the point cloud is dense.

- `field PointCloud2Point[] points`

    An array of points in the point cloud, where each point includes attributes such as position, intensity, normal, RGB color, moment invariants, and channel.

- `field varvalue{string} extended`

    Extended information about the point cloud.

## Structure: `PointCloud2Part`

The `PointCloud2Part` structure represents a part of a point cloud with additional attributes such as intensity, normal, RGB color, moment invariants, and channel. It includes information about the bounding box, density, offset, total length, and an array of points corresponding to the part.

- `field BoundingBox bounds`

    The bounding box that encloses the point cloud part.

- `field bool is_dense`

    A flag indicating whether the point cloud part is dense.

- `field uint32 points_offset`

    The offset of the points within the complete point cloud.

- `field uint32 points_total_len`

    The total length of the points within the complete point cloud.

- `field PointCloud2Point[] points`

    An array of points corresponding to the part of the point cloud, where each point includes attributes such as position, intensity, normal, RGB color, moment invariants, and channel.

- `field varvalue{string} extended`

    Extended information about the point cloud part.

## Structure: `PointCloud2Pointf`

The `PointCloud2Pointf` named array represents a point in a point cloud with single-precision floating-point values. It 
includes attributes such as position, intensity, normal, RGB color, moment invariants, and channel.

- `field Pointf point`

    The position of the point in three-dimensional space.

- `field single intensity`

    The intensity value of the point.

- `field Vector3f normal`

    The normal vector of the point.

- `field PixelRGBFloatPackedf rgb`

    The RGB color of the point.

- `field single[3] moment_invariants`

    The moment invariants of the point.

- `field single channel`

    The channel value of the point.

## Structure: `PointCloud2f`

The `PointCloud2f` structure represents a point cloud with additional attributes and single-precision floating-point values. It includes information about the bounding box, density, and an array of points.

- `field BoundingBoxf bounds`

    The bounding box that encloses the point cloud.

- `field bool is_dense`

    A flag indicating whether the point cloud is dense.

- `field PointCloud2Pointf[] points`

    An array of points in the point cloud, where each point includes attributes such as position, intensity, normal, RGB color, moment invariants, and channel.

- `field varvalue{string} extended`

    Extended information about the point cloud.

## Structure: `FreeformPointCloud`

The `FreeformPointCloud` structure represents a freeform point cloud with variable encoding and attributes. It includes information about the bounding box, encoding type, density, points, and extended information.

- `field BoundingBox bounds`

    The bounding box that encloses the freeform point cloud.

- `field string encoding`

    The encoding type used for representing the points in the freeform point cloud.

- `field bool is_dense`

    A flag indicating whether the freeform point cloud is dense.

- `field varvalue points`

    The points in the freeform point cloud, which can have a variable format depending on the encoding.

- `field varvalue{string} extended`

    Extended information about the freeform point cloud.

## Structure: `FreeformPointCloudPart`

The `FreeformPointCloudPart` structure represents a part of a freeform point cloud with variable encoding and attributes. It includes information about the bounding box, encoding type, density, offset, total length, points, and extended information.

- `field BoundingBox bounds`

    The bounding box that encloses the part of the freeform point cloud.

- `field string encoding`

    The encoding type used for representing the points in the freeform point cloud.

- `field bool is_dense`

    A flag indicating whether the part of the freeform point cloud is dense.

- `field uint32 points_offset`

    The offset of the points within the complete freeform point cloud.

- `field uint32 points_total_len`

    The total length of the points within the complete freeform point cloud.

- `field varvalue points`

    The points corresponding to the part of the freeform point cloud, which can have a variable format depending on the encoding.

- `field varvalue{string} extended`

    Extended information about the part of the freeform point cloud.

