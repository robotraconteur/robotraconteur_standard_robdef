# Service:  com.robotraconteur.bignum

Arbitrary precision number types.

## Standard Version

The standard version of this service is `0.10`.

## Structure: BigNum

The `BigNum` structure represents a signed arbitrary precision number in little endian format.

- `field uint8[] data`

    The data of the number in little endian format. The number is stored in base 256 with the least significant byte
    first. The number is stored in two's complement format. The number of bytes used is the minimum number of bytes.

## Structure: UnsignedBigNum

The `UnsignedBigNum` structure represents an unsigned arbitrary precision number in little endian format.
The number is stored in base 256 with the least significant byte first. The number of bytes used is the minimum number of bytes.

- `field uint8[] data`

## Structure: BigFloat

The `BigFloat` structure represents an arbitrary precision floating point number. Three BigNum are used to
represent the floating point number using `num`, `den`, and `radix`. The number is represented as `num/den*radix^exp`.

- `field BigNum num`

    The numerator of the number
- `field BigNum den`

    The denominator of the number

- `field BigNum radix`

    Unused
