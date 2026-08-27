---
sidebar_position: 6
---
# Treatment Template DTO

Represents a reusable treatment template that can be applied to create treatment plans. Templates define the default name, pricing, and treatment-specific configuration that gets copied onto a treatment plan when it's created.

## Structure

```json
{
  "id": "UUID",
  "createdOn": {
    "milliSeconds": 1784551020000
  },
  "clinicId": "UUID",
  "name": {
    "en": "Treatment name",
    "ar": "Treatment name"
  },
  "description": "Treatment description",
  "type": "Dental",
  "code": "D2740",
  "paintType": {
    "dtoName": "Crown"
  },
  "group": "Restorative",
  "billItemTemplateId": "UUID",
  "practice": {
    "dtoName": "Dental"
  },
  "treatmentSpecificInfo": {},
  "progressNotes": {},
  "paymentPlan": {}
}
```

## Fields

|Parameter|Type|Is required|Description|
|---|---|---|---|
|`id`|UUID|Optional|Unique identifier for the treatment template. Not present when creating a new template|
|`createdOn.milliSeconds`|Long|Required|Timestamp (epoch milliseconds) of when the template was created|
|`clinicId`|UUID|Required|Identifier of the clinic that owns this template|
|`name.en`|String|Required|Template name in English|
|`name.ar`|String|Required|Template name in Arabic|
|`description`|String|Optional|Free-text description of the treatment|
|`type`|String|Required|Category of the treatment this template creates (e.g. `Dental`)|
|`code`|String|Optional|Treatment/procedure code associated with this template (e.g. an ADA/CDT code)|
|`paintType.dtoName`|String (enum)|Optional|Visual marker/icon used to represent the resulting treatment on the tooth chart. One of `RCT`, `Filling`, `Crown`, `Extraction`, `Implant`, `PostAndCore`, `Sealant`, `Bridge`, `Veneer`, `Apicoectomy`|
|`group`|String|Required|Name of the group/category this template is organized under in the template list|
|`billItemTemplateId`|UUID|Required|Identifier of the bill item template used to generate charges for this treatment|
|`practice.dtoName`|String (enum)|Required|Practice/specialty this template belongs to (e.g. `Dental`)|
|`treatmentSpecificInfo`|Object|Required|Treatment-type-specific default configuration (e.g. treatment area, material) copied onto treatment plans created from this template|
|`progressNotes`|Object|Required|Default progress note configuration for treatment plans created from this template|
|`paymentPlan`|Object|Required|Default pricing configuration (rate, currency, tax, etc.) copied onto treatment plans created from this template|
