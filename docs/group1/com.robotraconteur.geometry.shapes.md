# Service: `com.robotraconteur.geometry.shapes`

The `com.robotraconteur.geometry.shapes` service provides definitions for various geometric shapes and related objects.

### Standard Version

The standard version of this service is `0.10`.

### Imports

This service imports the following packages:

- `com.robotraconteur.geometry`: Provides functionality for geometric operations and types.
- `com.robotraconteur.identifier`: Offers functionality for identifiers.
- `com.robotraconteur.color`: Defines color-related types.
- `com.robotraconteur.resource`: Provides functionality for resource-related operations.
- `com.robotraconteur.image`: Contains types related to images.
- `com.robotraconteur.fiducial`: Includes definitions for fiducials.

### Using Statements

This service uses the following statements to import specific types:

- `com.robotraconteur.geometry.Point`: Represents a point in 3D space.
- `com.robotraconteur.geometry.Pose`: Represents a position and orientation in 3D space.
- `com.robotraconteur.geometry.Vector2`: Represents a 2D vector.
- `com.robotraconteur.geometry.Vector3`: Represents a 3D vector.
- `com.robotraconteur.geometry.NamedPose`: Represents a named pose.
- `com.robotraconteur.geometry.SpatialInertia`: Represents the spatial inertia of an object.
- `com.robotraconteur.identifier.Identifier`: Represents an identifier.
- `com.robotraconteur.color.ColorRGB`: Represents an RGB color.
- `com.robotraconteur.color.ColorRGBA`: Represents an RGBA color.
- `com.robotraconteur.resource.ResourceIdentifier`: Represents a resource identifier.
- `com.robotraconteur.image.CompressedImage`: Represents an image that has been compressed.
- `com.robotraconteur.fiducial.Fiducial`: Represents a fiducial marker.

## Enum: `MeshType`

The `MeshType` enum represents the types of meshes used in the `com.robotraconteur.geometry.shapes` service.

- `mesh` (`0`): Represents a general mesh.
- `convex_mesh`: Represents a convex mesh.
- `sdf_mesh`: Represents a mesh used for signed distance field calculations.

This enum defines the different types of meshes that can be used.

## Struct: `Box`

The `Box` struct represents a box-shaped geometric object.

- `field double x`

    The length of the box along the x-axis.

- `field double y`

    The length of the box along the y-axis.

- `field double z`

    The length of the box along the z-axis.

This struct defines the dimensions of a box-shaped object.

## Struct: `Sphere`

The `Sphere` struct represents a spherical geometric object.

- `field double radius`

    The radius of the sphere.

This struct defines the radius of a sphere-shaped object.

## Struct: `Cylinder`

The `Cylinder` struct represents a cylindrical geometric object.

- `field double height`

    The height of the cylinder.

- `field double radius`

    The radius of the cylinder.

This struct defines the height and radius of a cylinder-shaped object.

## Struct: `Cone`

The `Cone` struct represents a conical geometric object.

- `field double height`

    The height of the cone.

- `field double radius`

    The radius of the base of the cone.

This struct defines the height and base radius of a cone-shaped object.

## Struct: `Capsule`

The `Capsule` struct represents a capsule-shaped geometric object.

- `field double height`

    The height of the capsule.

- `field double radius`

    The radius of the spherical caps of the capsule.

This struct

 defines the height and cap radius of a capsule-shaped object.

## Struct: `Plane`

The `Plane` struct represents a plane in 3D space using the equation `ax + by + cz + d = 0`.

- `field double a`

    The coefficient `a` in the plane equation.

- `field double b`

    The coefficient `b` in the plane equation.

- `field double c`

    The coefficient `c` in the plane equation.

- `field double d`

    The coefficient `d` in the plane equation.

This struct defines the coefficients of a plane equation.

## NamedArray: `MeshTriangle`

The `MeshTriangle` named array represents a triangle in a mesh.

- `field uint32 v1`

    The index of the first vertex of the triangle.

- `field uint32 v2`

    The index of the second vertex of the triangle.

- `field uint32 v3`

    The index of the third vertex of the triangle.

This named array defines the indices of the vertices that form a triangle in a mesh.

## Struct: `MeshTexture`

The `MeshTexture` struct represents the texture information for a mesh.

- `field CompressedImage image`

    The compressed image representing the texture.

- `field Vector2[] uvs`

    The UV coordinates of the texture mapped to the mesh vertices.

This struct defines the texture image and its UV coordinates for a mesh.

## Struct: `Mesh`

The `Mesh` struct represents a geometric mesh.

- `field MeshTriangle[] triangles`

    The triangles that make up the mesh.

- `field Point[] vertices`

    The vertices of the mesh.

- `field Vector3[] normals`

    The normals of the mesh.

- `field ColorRGB[] colors`

    The colors associated with the vertices of the mesh.

- `field MeshTexture{list} textures`

    The textures associated with the mesh.

- `field MeshType mesh_type`

    The type of the mesh.

This struct defines the triangles, vertices, normals, colors, textures, and type of a geometric mesh.

## Struct: `Material`

The `Material` struct represents the material properties of a shape object.

- `field ColorRGBA base_color_factor`

    The base color factor of the material.

- `field double metallic_factor`

    The metallic factor of the material.

- `field double roughness_factor`

    The roughness factor of the material.

- `field ColorRGBA emissive_factor`

    The emissive factor of the material.

- `field varvalue{string} extended`

    Extended information about the material.

This struct defines the base color, metallic factor, roughness factor, emissive factor, and extended information of a material.

## Struct: `ShapeObject`

The `ShapeObject` struct represents a shape object with its properties.

- `field Identifier name`

    The identifier of the shape object.

- `field varvalue{list} shapes`

    The shapes that make up the object.

- `field Pose{list} shape_poses`

    The poses of the shapes in the object.

- `field Material{list} shape_materials`

    The materials associated with the shapes in the object.

- `field SpatialInertia inertia`

    The spatial inertia of the object.

- `field Fiducial{list} fiducials`

    The fiducials associated with the shape object.

- `field varvalue{string} extended`

    Extended information about the shape object.

This struct defines the name, shapes, shape poses, shape materials, spatial inertia, fiducials, and extended information of a shape object.
