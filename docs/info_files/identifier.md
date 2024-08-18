# com.robotraconteur.identifier

Info file yaml entries for [com.robotraconteur.identifier](../group1/com.robotraconteur.identifier.md)

## Identifier

The identifier contains a name and a UUID. The identifier yaml entry can either contain `name` and
`uuid` fields, or a string that contains only a name.

UUIDs can be generated using the `uuidgen` command, or using an [online UUID generator](https://www.uuidgenerator.net/version4).

Many fields have a set of standard UUIDs. See the [Robot Raconteur Standard Identifiers](https://github.com/robotraconteur/robotraconteur_standard_identifiers)

An example `model` entry is shown below using both name and uuid:

```yaml
model:
    name: ABB_1200_5_90
    uuid: 9ad3c0ee-ec5e-4057-a297-d340e1484f01
```

An example of a `device` entry with just a name:

```yaml
device: robot
```

### name

Type: `string`

The name of the identifier. The name is a string that can be used to identify the identifier.

### uuid

Type: `string`

The UUID of the identifier. The UUID is a string that can be used to uniquely identify the identifier.
