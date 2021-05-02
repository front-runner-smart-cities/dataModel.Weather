Entität: WetterAlarm  
====================







- `alertSource`  



<details><summary><strong>full yaml details</strong></summary>    

WeatherAlert:    
  description: 'A weather alert generated by a user or device in a given location'    
  properties:    
    alertSource:    
      anyOf:    
        - description: 'Property. Identifier format of any NGSI entity'    
          maxLength: 256    
          minLength: 1    
          pattern: ^[\w\-\.\{\}\$\+\*\[\]`|~^@!,:\\]+$    
          type: string    
        - description: 'Property. Identifier format of any NGSI entity'    
          format: uri    
          type: string    
      description: 'Source of the alert'    
      type: Relationship    
      x-ngsi:    
        model: http://schema.org/URL.    
    category:    
      description: 'Category of the entity'    
      enum:    
        - weather    
      type: Property    
    data:    
      description: 'Payload containing the data retrieved.'    
      type: Property    
    dateIssued:    
      description: 'The date and time the item was issued in ISO8601 UTC format.'    
      format: date-time    
      type: Property    
      x-ngsi:    
        model: https://schema.org/DateTime    
    description:    
      description: 'Description of the Entity'    
      type: Property    
    severity:    
      description: 'Severity of the Alarm'    
      enum:    
        - informational    
        - low    
        - medium    
        - high    
        - critical    
      type: Property    
    subCategory:    
      description: 'Weather categories. Enum:'' avalanches,coastalEvent, coldWave, flood, fog, forestFire, heatWave, highTemperature, hurricane, ice, lowTemperature, rainfall, rain_flood, snow, snow_ice, thunderstorms, tornado, tropicalCyclone, tsunami, wind'''    
      enum:    
        - avalanches    
        - coastalEvent    
        - coldWave    
        - flood    
        - fog    
        - forestFire    
        - heatWave    
        - highTemperature    
        - hurricane    
        - ice    
        - lowTemperature    
        - rainfall    
        - rain_flood    
        - snow    
        - snow_ice    
        - thunderstorms    
        - tornado    
        - tropicalCyclone    
        - tsunami    
        - wind    
      type: Property    
    type:    
      description: 'NGSI Entity type. It has to be Alert.'    
      enum:    
        - Alert    
      type: Property    
    validFrom:    
      description: 'The start of the validity period for this forecast as a ISO8601 format'    
      format: date-time    
      type: Property    
      x-ngsi:    
        model: https://schema.org/DateTime    
    validTo:    
      description: 'The end of the validity period for this forecast as a ISO8601 format'    
      format: date-time    
      type: Property    
      x-ngsi:    
        model: https://schema.org/DateTime    
  required:    
    - id    
    - type    
    - alertSource    
    - category    
    - subCategory    
    - dateIssued    
  type: object    
```  
</details>    





  "severity": "medium",  
  "category": "weather",  
  "subCategory": "snow_ice",  
  "alertSource": "http://www.meteoalarm.eu",  
  "address": {  
    "addressCountry": "ES",  
    "addressRegion": "Huesca"  
  },  
  "dateIssued": "2016-03-14T13:54:01.00Z",  
  "type": "Alert",  
  "id": "WeatherAlert-83b872975414bfca10832e564a1bb416-7",  
  "validTo": "2016-03-14T23:59:00.00Z",  
  "validFrom": "2016-03-14T13:00:00.00Z"  
}  
```  




  "id": "WeatherAlert-83b872975414bfca10832e564a1bb416-7",  
  "type": "Alert",  
  "severity": {  
    "type": "Text",  
    "value": "medium"  
  },  
  "category": {  
    "type": "Text",  
    "value": "weather"  
  },  
  "subCategory": {  
    "type": "Text",  
    "value": "snow/ice"  
  },  
  "alertSource": {  
    "type": "Text",  
    "value": "http://www.meteoalarm.eu"  
  },  
  "address": {  
    "type": "PostalAddress",  
    "value": {  
      "addressCountry": "ES",  
      "addressRegion": "Huesca"  
    }  
  },  
  "dateIssued": {  
    "type": "DateTime",  
    "value": "2016-03-14T13:54:01.00Z"  
  },  
  "validTo": {  
    "type": "DateTime",  
    "value": "2016-03-14T23:59:00.00Z"  
  },  
  "validFrom": {  
    "type": "DateTime",  
    "value": "2016-03-14T13:00:00.00Z"  
  }  
}  
```  




  "id": "urn:ngsi-ld:WeatherAlert:WeatherAlert-83b872975414bfca10832e564a1bb416-7",  
  "type": "Alert",  
  "severity": {  
    "type": "Text",  
    "value": "medium"  
  },  
  "category": {  
    "type": "Text",  
    "value": "weather"  
  },  
  "subCategory": {  
    "type": "Text",  
    "value": "snow/ice"  
  },  
  "alertSource": {  
    "type": "Text",  
    "value": "http://www.meteoalarm.eu"  
  },  
  "address": {  
    "type": "PostalAddress",  
    "value": {  
      "addressCountry": "ES",  
      "addressRegion": "Huesca"  
    }  
  },  
  "dateIssued": {  
    "type": "DateTime",  
    "value": "2016-03-14T13:54:01.00Z"  
  },  
  "validTo": {  
    "type": "DateTime",  
    "value": "2016-03-14T23:59:00.00Z"  
  },  
  "validFrom": {  
    "type": "DateTime",  
    "value": "2016-03-14T13:00:00.00Z"  
  },  
  "@context": [  
    "https://smart-data-models.github.io/data-models/context.jsonld"  
  ]  
}  
```  




  "id": "urn:ngsi-ld:WeatherAlert:WeatherAlert-83b872975414bfca10832e564a1bb416-7",  
  "type": "Alert",  
  "severity": "medium",  
  "category": "weather",  
  "subCategory": "snow/ice",  
  "alertSource": "http://www.meteoalarm.eu",  
  "address": {  
    "addressCountry": "ES",  
    "addressRegion": "Huesca"  
  },  
  "dateIssued": "2016-03-14T13:54:01.00Z",  
  "validTo": "2016-03-14T23:59:00.00Z",  
  "validFrom": "2016-03-14T13:00:00.00Z",  
  "@context": [  
    "https://smart-data-models.github.io/data-models/context.jsonld"  
  ]  
}  
```  