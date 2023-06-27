## Service: `com.robotraconteur.datatype`

The `com.robotraconteur.datatype` service provides definitions and information about data types used in Robot Raconteur.

### Standard Version

The standard version of this service is `0.10`.

## Enum: `DataTypeCode`

The `DataTypeCode` enum represents the codes for various data types used in Robot Raconteur.

- `void_c` (`0`): Represents a void data type.
- `double_c`: Represents a double precision floating-point data type.
- `single_c`: Represents a single precision floating-point data type.
- `int8_c`: Represents a signed 8-bit integer data type.
- `uint8_c`: Represents an unsigned 8-bit integer data type.
- `int16_c`: Represents a signed 16-bit integer data type.
- `uint16_c`: Represents an unsigned 16-bit integer data type.
- `int32_c`: Represents a signed 32-bit integer data type.
- `uint32_c`: Represents an unsigned 32-bit integer data type.
- `int64_c`: Represents a signed 64-bit integer data type.
- `uint64_c`: Represents an unsigned 64-bit integer data type.
- `string_c`: Represents a string data type.
- `cdouble_c`: Represents a complex double precision floating-point data type.
- `csingle_c`: Represents a complex single precision floating-point data type.
- `bool_c`: Represents a boolean data type.
- `structure_c` (`101`): Represents a structure data type.
- `vector_c`: Represents a vector data type.
- `dictionary_c`: Represents a dictionary data type.
- `object_c`: Represents an object data type.
- `varvalue_c`: Represents a variant value data type.
- `varobject_c`: Represents a variant object data type.
- `list_c` (`108`): Represents a list data type.
- `pod_c`: Represents a plain old data (POD) data type.
- `pod_array_c`: Represents an array of POD data type.
- `pod_multidimarray_c`: Represents a multidimensional array of POD data type.
- `enum_c`: Represents an enum data type.
- `namedtype_c`: Represents a named type data type.
- `namedarray_c`: Represents a named array data type.
- `namedarray_array_c`: Represents an array of named arrays data type.
- `namedarray_multidimarray_c`: Represents a multidimensional array of named arrays data type.
- `multidimarray_c`: Represents a multidimensional array data type.

This enum defines the codes for various data types used in Robot Raconteur.

## Enum: `ArrayTypeCode`

The `ArrayTypeCode` enum represents the codes for array types used in Robot Raconteur.

- `none_c` (`0`): Represents no array type.
- `array_c`: Represents a standard array type.
- `multidimarray_c`: Represents a multidimensional array type.

This enum defines the codes for array types used in Robot Raconteur.

## Enum: `ContainerTypeCode`

The `ContainerTypeCode` enum represents the codes for container types used in Robot Raconteur.

- `none_c` (`0`): Represents no container type.
- `list_c`: Represents a list container type.
- `map_int32_c`: Represents a map container type with `int32` keys.
- `map_string_c`: Represents a map container type with string keys.
- `generator_c`: Represents a generator container type.

This enum defines the codes for container types used in Robot Raconteur.

## Struct: `DataType`

The `DataType` struct represents a data type in Robot Raconteur.

- `

field string name`

    The name of the data type.

- `field DataTypeCode type_code`

    The code representing the data type.

- `field string type_string`

    The string representation of the data type.

- `field ArrayTypeCode array_type_code`

    The code representing the array type of the data type.

- `field bool array_var_len`

    Indicates whether the array length is variable.

- `field uint32[] array_len`

    The lengths of the array dimensions.

- `field ContainerTypeCode container_type_code`

    The code representing the container type of the data type.



