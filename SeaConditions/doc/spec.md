Entity: SeaConditions  
=====================  
[Open License](https://github.com/smart-data-models//dataModel.Weather/blob/master/SeaConditions/LICENSE.md)  
[document generated automatically](https://docs.google.com/presentation/d/e/2PACX-1vTs-Ng5dIAwkg91oTTUdt8ua7woBXhPnwavZ0FxgR8BsAI_Ek3C5q97Nd94HS8KhP-r_quD4H0fgyt3/pub?start=false&loop=false&delayms=3000#slide=id.gb715ace035_0_60)  
Global description: **This entity contains a harmonised geographic description of sea conditions**  

## List of properties  

- `address`: The mailing address  - `alternateName`: An alternative name for this item  - `areaServed`: The geographic area where a service or offered item is provided  - `dataProvider`: A sequence of characters identifying the provider of the harmonised data entity.  - `dateCreated`: Entity creation timestamp. This will usually be allocated by the storage platform.  - `dateModified`: Timestamp of the last modification of the entity. This will usually be allocated by the storage platform.  - `dateObserved`: The date and time of this observation in ISO8601 UTC format.  - `description`: A description of this item  - `id`: Unique identifier of the entity  - `location`: Geojson reference to the item. It can be Point, LineString, Polygon, MultiPoint, MultiLineString or MultiPolygon  - `name`: The name of this item.  - `owner`: A List containing a JSON encoded sequence of characters referencing the unique Ids of the owner(s)  - `pH`: Acidity or basicity of an aqueous solution.  - `salinity`: Amount of salts dissolved in water.  - `seeAlso`: list of uri pointing to additional resources about the item  - `source`: A sequence of characters giving the original source of the entity data as a URL. Recommended to be the fully qualified domain name of the source provider, or the URL to the source object.  - `surfaceTemperature`: Sea surface temperature.  - `type`: NGSI-LD Entity Type. It has to be SeaConditions  - `waveHeight`: Height of the waves.  - `waveLevel`: It indicates the height of the waves and also measures the swell of the sea.  - `wavePeriod`: Indicates the time between the crests of a wave.    
Required properties  
- `id`  - `type`  ## Data Model description of properties  
Sorted alphabetically (click for details)  
<details><summary><strong>full yaml details</strong></summary>    
```yaml  
SeaConditions:    
  description: 'This entity contains a harmonised geographic description of sea conditions'    
  properties:    
    address:    
      description: 'The mailing address'    
      properties:    
        addressCountry:    
          description: 'Property. The country. For example, Spain. Model:''https://schema.org/addressCountry'''    
          type: string    
        addressLocality:    
          description: 'Property. The locality in which the street address is, and which is in the region. Model:''https://schema.org/addressLocality'''    
          type: string    
        addressRegion:    
          description: 'Property. The region in which the locality is, and which is in the country. Model:''https://schema.org/addressRegion'''    
          type: string    
        postOfficeBoxNumber:    
          description: 'Property. The post office box number for PO box addresses. For example, 03578. Model:''https://schema.org/postOfficeBoxNumber'''    
          type: string    
        postalCode:    
          description: 'Property. The postal code. For example, 24004. Model:''https://schema.org/https://schema.org/postalCode'''    
          type: string    
        streetAddress:    
          description: 'Property. The street address. Model:''https://schema.org/streetAddress'''    
          type: string    
      type: Property    
      x-ngsi:    
        model: https://schema.org/address    
    alternateName:    
      description: 'An alternative name for this item'    
      type: Property    
    areaServed:    
      description: 'The geographic area where a service or offered item is provided'    
      type: Property    
      x-ngsi:    
        model: https://schema.org/Text    
    dataProvider:    
      description: 'A sequence of characters identifying the provider of the harmonised data entity.'    
      type: Property    
    dateCreated:    
      description: 'Entity creation timestamp. This will usually be allocated by the storage platform.'    
      format: date-time    
      type: Property    
    dateModified:    
      description: 'Timestamp of the last modification of the entity. This will usually be allocated by the storage platform.'    
      format: date-time    
      type: Property    
    dateObserved:    
      description: 'The date and time of this observation in ISO8601 UTC format.'    
      format: date-time    
      type: Property    
      x-ngsi:    
        model: https://schema.org/DateTime    
    description:    
      description: 'A description of this item'    
      type: Property    
    id:    
      anyOf: &seaconditions_-_properties_-_owner_-_items_-_anyof    
        - description: 'Property. Identifier format of any NGSI entity'    
          maxLength: 256    
          minLength: 1    
          pattern: ^[\w\-\.\{\}\$\+\*\[\]`|~^@!,:\\]+$    
          type: string    
        - description: 'Property. Identifier format of any NGSI entity'    
          format: uri    
          type: string    
      description: 'Unique identifier of the entity'    
      type: Property    
    location:    
      description: 'Geojson reference to the item. It can be Point, LineString, Polygon, MultiPoint, MultiLineString or MultiPolygon'    
      oneOf:    
        - description: 'Geoproperty. Geojson reference to the item. Point'    
          properties:    
            bbox:    
              items:    
                type: number    
              minItems: 4    
              type: array    
            coordinates:    
              items:    
                type: number    
              minItems: 2    
              type: array    
            type:    
              enum:    
                - Point    
              type: string    
          required:    
            - type    
            - coordinates    
          title: 'GeoJSON Point'    
          type: object    
        - description: 'Geoproperty. Geojson reference to the item. LineString'    
          properties:    
            bbox:    
              items:    
                type: number    
              minItems: 4    
              type: array    
            coordinates:    
              items:    
                items:    
                  type: number    
                minItems: 2    
                type: array    
              minItems: 2    
              type: array    
            type:    
              enum:    
                - LineString    
              type: string    
          required:    
            - type    
            - coordinates    
          title: 'GeoJSON LineString'    
          type: object    
        - description: 'Geoproperty. Geojson reference to the item. Polygon'    
          properties:    
            bbox:    
              items:    
                type: number    
              minItems: 4    
              type: array    
            coordinates:    
              items:    
                items:    
                  items:    
                    type: number    
                  minItems: 2    
                  type: array    
                minItems: 4    
                type: array    
              type: array    
            type:    
              enum:    
                - Polygon    
              type: string    
          required:    
            - type    
            - coordinates    
          title: 'GeoJSON Polygon'    
          type: object    
        - description: 'Geoproperty. Geojson reference to the item. MultiPoint'    
          properties:    
            bbox:    
              items:    
                type: number    
              minItems: 4    
              type: array    
            coordinates:    
              items:    
                items:    
                  type: number    
                minItems: 2    
                type: array    
              type: array    
            type:    
              enum:    
                - MultiPoint    
              type: string    
          required:    
            - type    
            - coordinates    
          title: 'GeoJSON MultiPoint'    
          type: object    
        - description: 'Geoproperty. Geojson reference to the item. MultiLineString'    
          properties:    
            bbox:    
              items:    
                type: number    
              minItems: 4    
              type: array    
            coordinates:    
              items:    
                items:    
                  items:    
                    type: number    
                  minItems: 2    
                  type: array    
                minItems: 2    
                type: array    
              type: array    
            type:    
              enum:    
                - MultiLineString    
              type: string    
          required:    
            - type    
            - coordinates    
          title: 'GeoJSON MultiLineString'    
          type: object    
        - description: 'Geoproperty. Geojson reference to the item. MultiLineString'    
          properties:    
            bbox:    
              items:    
                type: number    
              minItems: 4    
              type: array    
            coordinates:    
              items:    
                items:    
                  items:    
                    items:    
                      type: number    
                    minItems: 2    
                    type: array    
                  minItems: 4    
                  type: array    
                type: array    
              type: array    
            type:    
              enum:    
                - MultiPolygon    
              type: string    
          required:    
            - type    
            - coordinates    
          title: 'GeoJSON MultiPolygon'    
          type: object    
      type: Geoproperty    
    name:    
      description: 'The name of this item.'    
      type: Property    
    owner:    
      description: 'A List containing a JSON encoded sequence of characters referencing the unique Ids of the owner(s)'    
      items:    
        anyOf: *seaconditions_-_properties_-_owner_-_items_-_anyof    
        description: 'Property. Unique identifier of the entity'    
      type: Property    
    pH:    
      description: 'Acidity or basicity of an aqueous solution.'    
      maximum: 14    
      minimum: 0    
      type: Property    
      x-ngsi:    
        model: https://schema.org/Number    
    salinity:    
      description: 'Amount of salts dissolved in water.'    
      minimum: 0    
      type: Property    
      x-ngsi:    
        model: https://schema.org/Number    
        units: 'Parts per thousand'    
    seeAlso:    
      description: 'list of uri pointing to additional resources about the item'    
      oneOf:    
        - items:    
            format: uri    
            type: string    
          minItems: 1    
          type: array    
        - format: uri    
          type: string    
      type: Property    
    source:    
      description: 'A sequence of characters giving the original source of the entity data as a URL. Recommended to be the fully qualified domain name of the source provider, or the URL to the source object.'    
      type: Property    
    surfaceTemperature:    
      description: 'Sea surface temperature.'    
      type: Property    
      x-ngsi:    
        model: https://schema.org/Number    
        units: 'Celsius degrees'    
    type:    
      description: 'NGSI-LD Entity Type. It has to be SeaConditions'    
      enum:    
        - SeaConditions    
      type: Property    
    waveHeight:    
      description: 'Height of the waves.'    
      type: Property    
      x-ngsi:    
        model: https://schema.org/Number    
        units: Meters    
    waveLevel:    
      description: 'It indicates the height of the waves and also measures the swell of the sea.'    
      maximum: 9    
      minimum: 0    
      type: Property    
      x-ngsi:    
        model: https://schema.org/Number    
        units: 'Douglas sea scale'    
    wavePeriod:    
      description: 'Indicates the time between the crests of a wave.'    
      type: Property    
      x-ngsi:    
        model: https://schema.org/Number    
        units: Seconds    
  required:    
    - id    
    - type    
  type: object    
```  
</details>    
## Example payloads    
#### SeaConditions NGSI-v2 key-values Example    
Here is an example of a SeaConditions in JSON-LD format as key-values. This is compatible with NGSI-v2 when  using `options=keyValues` and returns the context data of an individual entity.  
```json  
{  
  "id": "SeaCondition-PlayaLevante-Benidorm-123456",  
  "type": "SeaConditions",  
  "dateObserved": "2021-02-20T06:45:00Z",  
  "location": {  
    "type": "Point",  
    "coordinates": [  
      -8.768460000000001,  
      42.60214472222222  
    ]  
  },  
  "name": "Mar en la Playa Levante",  
  "description": "Información del estado del mar en la playa Levante",  
  "address": {  
    "addressCountry": "ES",  
    "addressLocality": "Benidorm"  
  },  
  "dataProvider": "Water-sensor-12345",  
  "waveLevel": 1,  
  "surfaceTemperature": 14.7,  
  "waveHeight": 0.05,  
  "wavePeriod": 1.5,  
  "pH": 8.5,  
  "salinity": 35  
}  
```  
#### SeaConditions NGSI-v2 normalized Example    
Here is an example of a SeaConditions in JSON-LD format as normalized. This is compatible with NGSI-v2 when not using options and returns the context data of an individual entity.  
```json  
{  
  "id": "SeaCondition-PlayaLevante.Benidorm.123456",  
  "type": "SeaConditions",  
  "dateCreated": {  
    "type": "DateTime",  
    "value": "2021-02-20T06:45:00Z"  
  },  
  "dateModified": {  
    "type": "DateTime",  
    "value":  "2021-02-20T06:45:00Z"  
  },  
  "source": {  
    "type": "Text",  
    "value": ""  
  },  
  "name": {  
    "type": "Text",  
    "value": "Mar en la Playa Levante"  
  },  
  "alternateName": {  
    "type": "Text",  
    "value": "Playa Levante"  
  },  
  "description": {  
    "type": "Text",  
    "value": "Información del estado del mar en la playa Levante"  
  },  
  "dataProvider": {  
    "type": "Text",  
    "value": "Water-sensor-12345"  
  },  
  "owner": {  
    "type": "StructuredValue",  
    "value": [  
      "urn:ngsi-ld:SeaConditions:items:JVPZ:12516420",  
      "urn:ngsi-ld:SeaConditions:items:XVAE:29040891"  
    ]  
  },  
  "seeAlso": {  
    "type": "StructuredValue",  
    "value": [  
      "urn:ngsi-ld:SeaConditions:items:KFKA:73977455",  
      "urn:ngsi-ld:SeaConditions:items:GPZI:53207694"  
    ]  
  },  
  "location": {  
    "type": "geo:json",  
    "value": {  
      "type": "Point",  
      "coordinates": [  
        -8.768460000000001,  
        42.60214472222222  
      ]  
    }  
  },  
  "address": {  
    "type": "StructuredValue",  
    "value": {  
      "streetAddress": "",  
      "addressLocality": "Benidorm",  
      "addressRegion": "Valencia",  
      "addressCountry": "ES",  
      "postalCode": "",  
      "postOfficeBoxNumber": ""  
    }  
  },  
  "areaServed": {  
    "type": "Text",  
    "value": ""  
  },  
  "waveLevel": {  
    "type": "Number",  
    "value": 1  
  },  
  "surfaceTemperature": {  
    "type": "Number",  
    "value": 14.7  
  },  
  "waveHeight": {  
    "type": "Number",  
    "value": 0.05  
  },  
  "wavePeriod": {  
    "type": "Number",  
    "value": 1.5  
  },  
  "pH": {  
    "type": "Number",  
    "value": 8.5  
  },  
  "salinity": {  
    "type": "Number",  
    "value": 35  
  },  
  "dateObserved": {  
    "type": "Number",  
    "value": "2021-02-20T06:45:00Z"  
  },  
  "@context": [  
    "https://smartdatamodels.org/context.jsonld"  
  ]  
}  
```  
#### SeaConditions NGSI-LD key-values Example    
Here is an example of a SeaConditions in JSON-LD format as key-values. This is compatible with NGSI-LD when  using `options=keyValues` and returns the context data of an individual entity.  
```json  
{"@context": ["https://smaertdatamodels.org/context.jsonld",  
              "https://uri.etsi.org/ngsi-ld/v1/ngsi-ld-core-context.jsonld"],  
 "id": "urn:ngsi-ld:SeaCondition:SeaCondition-PlayaLevante-Benidorm-123456",  
 "type": "SeaConditions",  
 "dateObserved": "2021-02-20T06:45:00Z",  
 "location": {"coordinates": [-8.768460000000001, 42.60214472222222],  
              "type": "Point"},  
 "name": "Mar en la Playa Levante",  
 "description": "InformaciÃ³n del estado del mar en la playa Levante",  
 "address": {"addressCountry": "ES",  
             "addressLocality": "Benidorm"},  
 "dataProvider": "Water-sensor-12345",  
 "waveLevel": 1,  
 "surfaceTemperature": 14.7,  
 "waveHeight": 0.05,  
 "wavePeriod": 1.5,  
 "pH": 8.5,  
 "salinity": 35}  
```  
#### SeaConditions NGSI-LD normalized Example    
Here is an example of a SeaConditions in JSON-LD format as normalized. This is compatible with NGSI-LD when not using options and returns the context data of an individual entity.  
```json  
{  
  "id": "urn:ngsi-ld:SeaCondition:SeaCondition-PlayaLevante-Benidorm-123456",  
  "type": "SeaConditions",  
  "dateCreated": {  
    "type": "Property",  
    "value": {  
      "@type": "DateTime",  
      "@value": "2021-02-20T06:45:00Z"  
    }  
  },  
  "dateModified": {  
    "type": "Property",  
    "value": {  
      "@type": "DateTime",  
      "@value": "2021-02-20T06:45:00Z"  
    }  
  },  
  "source": {  
    "type": "Property",  
    "value": ""  
  },  
  "name": {  
    "type": "Property",  
    "value": "Mar en la Playa Levante"  
  },  
  "alternateName": {  
    "type": "Property",  
    "value": "Playa Levante"  
  },  
  "description": {  
    "type": "Property",  
    "value": "InformaciÃ³n del estado del mar en la playa Levante"  
  },  
  "dataProvider": {  
    "type": "Property",  
    "value": "Water-sensor-12345"  
  },  
  "owner": {  
    "type": "Property",  
    "value": [  
      "urn:ngsi-ld:SeaConditions:items:JVPZ:12516420",  
      "urn:ngsi-ld:SeaConditions:items:XVAE:29040891"  
    ]  
  },  
  "seeAlso": {  
    "type": "Property",  
    "value": [  
      "urn:ngsi-ld:SeaConditions:items:KFKA:73977455",  
      "urn:ngsi-ld:SeaConditions:items:GPZI:53207694"  
    ]  
  },  
  "location": {  
    "type": "Property",  
    "value": {  
      "type": "Point",  
      "coordinates": [  
        -8.768460000000001, 42.60214472222222  
      ]  
    }  
  },  
  "address": {  
    "type": "Property",  
    "value": {  
      "streetAddress": "",  
      "addressLocality": "Benidorm",  
      "addressRegion": "Valencia",  
      "addressCountry": "ES",  
      "postalCode": "",  
      "postOfficeBoxNumber": ""  
    }  
  },  
  "areaServed": {  
    "type": "Property",  
    "value": ""  
  },  
  "waveLevel": {  
    "type": "Property",  
    "value": 1  
  },  
  "surfaceTemperature": {  
    "type": "Property",  
    "value": 14.7  
  },  
  "waveHeight": {  
    "type": "Property",  
    "value": 0.05  
  },  
  "wavePeriod": {  
    "type": "Property",  
    "value": 1.5  
  },  
  "pH": {  
    "type": "Property",  
    "value": 8.5  
  },  
  "salinity": {  
    "type": "Property",  
    "value": 35  
  },  
  "dateObserved": {  
    "type": "Property",  
    "value": "2021-02-20T06:45:00Z"  
  },  
  "@context": [  
    "https://smartdatamodels.org/context.jsonld"  
  ]  
}  
```  
