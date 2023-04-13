# NGSI-LD entity attributes

This custom node is a simple node that allows to append, update, upsert or replace attributes of NGSI-LD entity.

![](https://raw.githubusercontent.com/lets-fiware/node-red-contrib-NGSI-LD/gh-pages/images/entity-attributes/entity-attributes-01.png)

## Contents

<details>
<summary><strong>Details</strong></summary>

-   [Append attributes](#append-attributes)
-   [Update attributes](#update-attributes)
-   [Upsert attributes](#upsert-attributes)

</details>

## Append attributes

It allows to append attributes of NGSI-LD entity.

### Properties

![](https://raw.githubusercontent.com/lets-fiware/node-red-contrib-NGSI-LD/gh-pages/images/entity-attributes/entity-attributes-02.png)

| Property       | Description                     |
| -------------- | ------------------------------- |
| Name           | A name for a node instance      |
| Broker         | An endpoint of a NGSI-LD broker |
| Action type    | `append`                        |
| Entity id      | Id of the concerned entity      |
| @context       | NGSI-LD @context                |

### Example

#### Input1

Payload *JSON Object*

A `msg.payload` should contain an object with the attributes.

```
{
  "batteryLevel": {
    "type": "Property",
    "value": 0.9,
    "unitCode": "C62"
  },
  "controlledAsset": {
    "type": "Relationship",
    "object": "urn:ngsi-ld:Building:barn002"
  }
}
```

#### Input2

Payload *JSON Object*

A `msg.payload` should contain information related to the attributes to append.
The values in the payload may overwrite properties.

| Name     | Data type   | Description                |
| -------- | ----------- | -------------------------- |
| entityId | string      | Id of the concerned entity |
| attrs    | JSON Object | Attributes to append       |

```
{
  "entityId": "urn:ngsi-ld:TemperatureSensor:002",
  "attrs": {
    "batteryLevel": {
      "type": "Property",
      "value": 0.9,
      "unitCode": "C62"
    },
    "controlledAsset": {
      "type": "Relationship",
      "object": "urn:ngsi-ld:Building:barn002"
    }
  }
}
```

#### Output

Payload *Number* or *null*

A `msg.payload` contains a status code.

```
204
```

```
null
```

## Update attributes

It allows to update attributes of NGSI-LD entity.

### Properties

![](https://raw.githubusercontent.com/lets-fiware/node-red-contrib-NGSI-LD/gh-pages/images/entity-attributes/entity-attributes-03.png)

| Property       | Description                     |
| -------------- | ------------------------------- |
| Name           | A name for a node instance      |
| Broker         | An endpoint of a NGSI-LD broker |
| Action type    | `append`                        |
| Entity id      | Id of the concerned entity      |
| @context       | NGSI-LD @context                |

### Example

#### Input1

Payload *JSON Object*

A `msg.payload` should contain an object with the attributes.

```
{
  "batteryLevel": {
    "type": "Property",
    "value": 0.9,
    "unitCode": "C62"
  },
  "controlledAsset": {
    "type": "Relationship",
    "object": "urn:ngsi-ld:Building:barn002"
  }
}
```

#### Input2

Payload *JSON Object*

A `msg.payload` should contain information related to the attributes to update.
The values in the payload may overwrite properties.

| Name     | Data type   | Description                |
| -------- | ----------- | -------------------------- |
| entityId | string      | Id of the concerned entity |
| attrs    | JSON Object | Attributes to update       |

```
{
  "entityId": "urn:ngsi-ld:TemperatureSensor:002",
  "attrs": {
    "batteryLevel": {
      "type": "Property",
      "value": 0.9,
      "unitCode": "C62"
    },
    "controlledAsset": {
      "type": "Relationship",
      "object": "urn:ngsi-ld:Building:barn002"
    }
  }
}
```

#### Output

Payload *Number* or *null*

A `msg.payload` contains a status code.

```
204
```

```
null
```

## Upsert attributes

It allows to upsert attributes of NGSI-LD entity.

### Properties

![](https://raw.githubusercontent.com/lets-fiware/node-red-contrib-NGSI-LD/gh-pages/images/entity-attributes/entity-attributes-04.png)

| Property       | Description                     |
| -------------- | ------------------------------- |
| Name           | A name for a node instance      |
| Broker         | An endpoint of a NGSI-LD broker |
| Action type    | `append`                        |
| Entity id      | Id of the concerned entity      |
| @context       | NGSI-LD @context                |

### Example

#### Input1

Payload *JSON Object*

A `msg.payload` should contain an object with the attributes.

```
{
  "batteryLevel": {
    "type": "Property",
    "value": 0.9,
    "unitCode": "C62"
  },
  "controlledAsset": {
    "type": "Relationship",
    "object": "urn:ngsi-ld:Building:barn002"
  }
}
```

#### Input2

Payload *JSON Object*

A `msg.payload` should contain information related to the attributes to upsert.
The values in the payload may overwrite properties.

| Name     | Data type   | Description                |
| -------- | ----------- | -------------------------- |
| entityId | string      | Id of the concerned entity |
| attrs    | JSON Object | Attributes to upsert       |

```
{
  "entityId": "urn:ngsi-ld:TemperatureSensor:002",
  "attrs": {
    "batteryLevel": {
      "type": "Property",
      "value": 0.9,
      "unitCode": "C62"
    },
    "controlledAsset": {
      "type": "Relationship",
      "object": "urn:ngsi-ld:Building:barn002"
    }
  }
}
```

#### Output

Payload *Number* or *null*

A `msg.payload` contains a status code.

```
204
```

```
null
```