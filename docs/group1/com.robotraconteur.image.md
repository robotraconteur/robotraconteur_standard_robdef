## Service: `com.robotraconteur.image`

The `com.robotraconteur.image` service provides functionality for representing images and image-related data.

### Standard Version

The standard version of this service is `0.10`.

### Imports

This service imports the following packages:

- `com.robotraconteur.sensordata`: Includes definitions for sensor data.
- `com.robotraconteur.identifier`: Provides functionality for representing identifiers.
- `com.robotraconteur.resource`: Represents resources.

### Using Statements

This service uses the following statements to import specific types:

- `com.robotraconteur.sensordata.SensorDataHeader`: Represents the header of sensor data.
- `com.robotraconteur.identifier.Identifier`: Represents an identifier with a name and a UUID.
- `com.robotraconteur.resource.ResourceIdentifier`: Represents a resource identifier.

## Enum: `ImageEncoding`

The `ImageEncoding` enum represents the encoding types for images within the `com.robotraconteur.image` service.

- `unknown` (`0`): Represents an unknown image encoding.
- `rgb888` (`0x1000`): Represents the RGB888 image encoding.
- `rgba8888`: Represents the RGBA8888 image encoding.
- `bgr888`: Represents the BGR888 image encoding.
- `bgra8888`: Represents the BGRA8888 image encoding.
- `rgba16_16_16_16`: Represents the RGBA16_16_16_16 image encoding.
- `bgra16_16_16_16`: Represents the BGRA16_16_16_16 image encoding.
- `mono8` (`0x2000`): Represents the Mono8 image encoding.
- `mono16`: Represents the Mono16 image encoding.
- `mono32`: Represents the Mono32 image encoding.
- `mono_f16`: Represents the MonoF16 image encoding.
- `mono_f32`: Represents the MonoF32 image encoding.
- `mono_f64`: Represents the MonoF64 image encoding.
- `bayer_rggb8888` (`0x3000`): Represents the BayerRGGB8888 image encoding.
- `bayer_bggr8888`: Represents the BayerBGGR8888 image encoding.
- `bayer_gbrg8888`: Represents the BayerGBRG8888 image encoding.
- `bayer_grbg8888`: Represents the BayerGRBG8888 image encoding.
- `depth_u16` (`0x4000`): Represents the DepthU16 image encoding.
- `depth_i16`: Represents the DepthI16 image encoding.
- `depth_u32`: Represents the DepthU32 image encoding.
- `depth_i32`: Represents the DepthI32 image encoding.
- `depth_u64`: Represents the DepthU64 image encoding.
- `depth_i64`: Represents the DepthI64 image encoding.
- `depth_f32`: Represents the DepthF32 image encoding.
- `depth_f64`: Represents the DepthF64 image encoding.
- `freeform` (`0x5000`): Represents a freeform image encoding.
- `compressed` (`0x6000`): Represents a compressed image encoding.
- `other` (`0x8000`): Represents an image encoding not specified by the enum.

This enum provides predefined encoding types for images.

## Structure: `PixelRGB`

The `PixelRGB` structure represents an RGB pixel within the `com.robotraconteur.image` service.

- `field uint8 r`

    The red component of the pixel.

- `field uint8 g`

    The green component of the pixel.

- `field uint8 b`

    The blue component of the pixel.

The `PixelRGB` structure represents an RGB pixel with 8 bits per channel.

## Structure: `PixelRGBA`

The `PixelRGBA` structure represents an RGBA pixel within the `com.robotraconteur.image` service.

- `field uint8 r`

    The red component of the pixel.

- `field uint8 g`

    The green component of the pixel.

- `field uint8 b`

    The blue component of the pixel.

- `field uint8 a`

    The alpha (transparency) component of the pixel.

The `PixelRGBA` structure represents an RGBA pixel with 8 bits per channel, including an alpha channel for transparency.

## NamedArray: `PixelRGBFloatPacked`

The `PixelRGBFloatPacked` named array represents an RGB pixel with packed floating-point values within the `com.robotraconteur.image` service.

- `field double rgb`

    The packed RGB value as a double.

The `PixelRGBFloatPacked` named array is used with laser scan and point cloud data.

## NamedArray: `PixelRGBFloatPackedf`

The `PixelRGBFloatPackedf` named array represents an RGB pixel with packed floating-point values within the `com.robotraconteur.image` service.

- `field single rgb`

    The packed RGB value as a single-precision floating-point number.

The `PixelRGBFloatPackedf` named array is used with laser scan and point cloud data.

## Structure: `ImageInfo`

The `ImageInfo` structure represents information about an image within the `com.robotraconteur.image` service.

- `field SensorDataHeader data_header`

    The header of the sensor data associated with the image.

- `field uint32 height`

    The height of the image in pixels.

- `field uint32 width`

    The width of the image in pixels.

- `field uint32 step`

    The step size (in bytes) between two consecutive rows of the image.

- `field ImageEncoding encoding`

    The encoding type of the image.

- `field varvalue{string} extended`

    Extended information about the image.

The `ImageInfo` structure provides detailed information about an image, including its dimensions, encoding type, and associated sensor data.

## Structure: `FreeformImageInfo`

The `FreeformImageInfo` structure represents information about a freeform image within the `com.robotraconteur.image` service.

- `field ImageInfo image_info`

    The information of the underlying image.

- `field string encoding`

    The encoding type of the freeform image.

- `field varvalue{string} extended`

    Extended information about the freeform image.

The `FreeformImageInfo` structure provides information about a freeform image, including the encoding type and extended information.

## Structure: `Image`

The `Image` structure represents an image within the `com.robotraconteur.image` service.

- `field ImageInfo image_info`

    The information of the image.

- `field uint8[] data`

    The image data as a sequence of bytes.

The `Image` structure encapsulates an image with its associated information and data.

## Structure: `CompressedImage`

The `CompressedImage` structure represents a compressed image within the `com.robotraconteur.image` service.

- `field ImageInfo image_info`

    The information of the compressed image.

- `field uint8[] data`

    The compressed image data as a sequence of bytes.

The `CompressedImage` structure represents an image that has been compressed using a specific encoding.

## Structure: `FreeformImage`

The `FreeformImage` structure represents a freeform image within the `com.robotraconteur.image` service.

- `field FreeformImageInfo image_info`

    The information of the freeform image.

- `field varvalue data`

    The data of the freeform image.

- `field varvalue{string} extended`

    Extended information about the freeform image.

The `FreeformImage` structure represents a freeform image, which can have arbitrary data and encoding.

## Structure: `ImagePart`

The `ImagePart` structure represents a part of an image within the `com.robotraconteur.image` service.

- `field ImageInfo image_info`

    The information of the image.

- `field uint32 data_offset`

    The offset of the data part within the complete image data.

- `field uint32 data_total_len`

    The total length of the complete image data.

- `field uint8[] data_part`

    The data part of the image as a sequence of bytes.

The `ImagePart` structure represents a partial section of an image, allowing for transmitting and processing large images in parts.

## Structure: `CompressedImagePart`

The `CompressedImagePart` structure represents a part of a compressed image within the `com.robotraconteur.image` service.

- `field ImageInfo image_info`

    The information of the compressed image.

- `field uint32 data_offset`

    The offset of the data part within the complete compressed image data.

- `field uint32 data_total_len`

    The total length of the complete compressed image data.

- `field uint8[] data_part`

    The data part of the compressed image as a sequence of bytes.

The `CompressedImagePart` structure represents a partial section of a compressed image, enabling the transmission and processing of large compressed images in parts.

## Structure: `FreeformImagePart`

The `FreeformImagePart` structure represents a part of a freeform image within the `com.robotraconteur.image` service.

- `field FreeformImageInfo image_info`

    The information of the freeform image.

- `field uint32 data_offset`

    The offset of the data part within the complete freeform image data.

- `field uint32 data_total_len`

    The total length of the complete freeform image data.

- `field varvalue data_part`

    The data part of the freeform image.

- `field varvalue{string} extended`

    Extended information about the freeform image part.

The `FreeformImagePart` structure represents a partial section of a freeform image, enabling the transmission and processing of large freeform images in parts.

## Structure: `ImageResource`

The `ImageResource` structure represents an image that is stored as a resource within a 
`com.robotraconteur.resource.ResourceDevice` service.

- `field ResourceIdentifier image_resource`

    The resource identifier to retrieve the image.




