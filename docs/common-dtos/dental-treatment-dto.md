---
sidebar_position: 5
---

# Dental Treatment DTO  
  
Represents a dental treatment created for a patient, including the treatment details, affected teeth, progress notes, applied taxes, and payment breakdown.  
  
## Structure  
  
```json  
{  
  "id": "UUID",  
  "isDeleted": false,  
  "clinicId": "UUID",  
  "createdOn": {  
    "milliSeconds": 1784551020000  
  },  
  "name": {  
    "en": "Treatment name",  
    "ar": "Treatment name"  
  },  
  "status": "Planned",  
  "practiceEmrId": "UUID",  
  "treatmentTemplateId": "UUID",  
  "uiId": "mrtbw82r5ezh",  
  "treatmentSpecificInfo": {  
    "dentalTreatmentArea": "Tooth",  
    "teethIdentifiers": [  
      {  
        "toothOrder": 13,  
        "isPrimary": false,  
        "isSupernumerary": false  
      }  
    ],  
    "material": "Metallic",  
    "type": "Dental"  
  },  
  "progressNotes": {  
    "progressNoteTemplates": [  
      {  
        "description": "ok",  
        "status": "Completed",  
        "lastEditedDate": {  
          "milliSeconds": 1784551020000  
        },  
        "extraInfo": {  
          "dentalTreatmentArea": "Mouth",  
          "teethIdentifiers": [],  
          "type": "Dental"  
        }  
      }  
    ]  
  },  
  "paintType": "Crown",  
  "notes": "",  
  "doctorId": "UUID",  
  "startDate": {  
    "date": "2026-07-20"  
  },  
  "isStarted": true,  
  "appliedTax": [  
    {  
      "taxId": "UUID",  
      "name": "VAT",  
      "percentage": 5.0,  
      "amount": 12.5  
    }  
  ],  
  "paymentDetails": {  
    "rate": 250.0,  
    "quantity": 1.0,  
    "currency": "AED",  
    "total": 250.0,  
    "discount": 0.0,  
    "insured": 0.0,  
    "tax": 12.5  
  },  
  "startTime": {  
    "milliSeconds": 1784558226210  
  }  
}  
```  
  
## Fields  
  
| Parameter                                                             | Type          | Is required | Description                                                                                                                                                                                   |  
| --------------------------------------------------------------------- | ------------- | ----------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |  
| `id`                                                                  | UUID          | Required    | Unique identifier for the treatment plan record                                                                                                                                               |  
| `isDeleted`                                                           | Boolean       | Required    | Whether the treatment plan has been soft-deleted                                                                                                                                              |  
| `clinicId`                                                            | UUID          | Required    | Identifier of the clinic that owns this treatment plan                                                                                                                                        |  
| `createdOn.milliSeconds`                                              | Long          | Required    | Timestamp (epoch milliseconds) of when the treatment plan was created                                                                                                                         |  
| `name.en`                                                             | String        | Required    | Treatment name in English                                                                                                                                                                     |  
| `name.ar`                                                             | String        | Required    | Treatment name in Arabic                                                                                                                                                                      |  
| `status`                                                              | String (enum) | Required    | Current state of the treatment plan. One of `Planned`, `Pending`, `Recommended`, `Existing`, `Completed`, `Cancelled`                                                                         |  
| `practiceEmrId`                                                       | UUID          | Optional    | Identifier linking the treatment plan to a record in the practice's EMR system                                                                                                                |  
| `treatmentTemplateId`                                                 | UUID          | Optional    | Identifier of the treatment template this plan was created from                                                                                                                               |  
| `uiId`                                                                | String        | Required    | Short identifier used to reference this treatment plan on the tooth chart / UI                                                                                                                |  
| `treatmentSpecificInfo`                                               | Object        | Required    | Details specific to the type of dental treatment applied                                                                                                                                      |  
| `treatmentSpecificInfo.dentalTreatmentArea`                           | String (enum) | Required    | Area the treatment applies to. One of `Surfaces`, `Tooth`, `TeethRange`, `Arch`, `Mouth`                                                                                                      |  
| `treatmentSpecificInfo.teethIdentifiers`                              | Array[object] | Required    | List of teeth this treatment applies to. Empty when the treatment area is not tooth-specific                                                                                                  |  
| `treatmentSpecificInfo.teethIdentifiers[].toothOrder`                 | Integer       | Required    | Tooth number according to the clinic's numbering system                                                                                                                                       |  
| `treatmentSpecificInfo.teethIdentifiers[].isPrimary`                  | Boolean       | Required    | Whether the tooth is a primary (baby) tooth                                                                                                                                                   |  
| `treatmentSpecificInfo.teethIdentifiers[].isSupernumerary`            | Boolean       | Required    | Whether the tooth is a supernumerary (extra) tooth                                                                                                                                            |  
| `treatmentSpecificInfo.material`                                      | String (enum) | Optional    | Material used for the treatment (e.g. `Metallic`)                                                                                                                                             |  
| `treatmentSpecificInfo.type`                                          | String (enum) | Required    | Category of the treatment (e.g. `Dental`)                                                                                                                                                     |  
| `progressNotes`                                                       | Object        | Optional    | Container for the progress notes recorded against this treatment plan                                                                                                                         |  
| `progressNotes.progressNoteTemplates`                                 | Array[object] | Optional    | List of progress note entries recorded during treatment                                                                                                                                       |  
| `progressNotes.progressNoteTemplates[].description`                   | String        | Optional    | Free-text note describing the progress made                                                                                                                                                   |  
| `progressNotes.progressNoteTemplates[].status`                        | String (enum) | Required    | Status of the progress note (e.g. `Completed`)                                                                                                                                                |  
| `progressNotes.progressNoteTemplates[].lastEditedDate.milliSeconds`   | Long          | Required    | Timestamp (epoch milliseconds) of the last edit to this progress note                                                                                                                         |  
| `progressNotes.progressNoteTemplates[].extraInfo.dentalTreatmentArea` | String (enum) | Optional    | Area the progress note refers to. One of `Surfaces`, `Tooth`, `TeethRange`, `Arch`, `Mouth`                                                                                                   |  
| `progressNotes.progressNoteTemplates[].extraInfo.teethIdentifiers`    | Array[object] | Optional    | Teeth referenced by this progress note, using the same shape as `treatmentSpecificInfo.teethIdentifiers`                                                                                      |  
| `progressNotes.progressNoteTemplates[].extraInfo.type`                | String (enum) | Optional    | Category of the progress note (e.g. `Dental`)                                                                                                                                                 |  
| `paintType`                                                           | String (enum) | Optional    | Visual marker/icon used to represent the treatment on the tooth chart. One of `RCT`, `Filling`, `Crown`, `Extraction`, `Implant`, `PostAndCore`, `Sealant`, `Bridge`, `Veneer`, `Apicoectomy` |  
| `notes`                                                               | String        | Optional    | Free-text notes about the treatment plan                                                                                                                                                      |  
| `doctorId`                                                            | UUID          | Required    | Identifier of the doctor assigned to the treatment                                                                                                                                            |  
| `startDate.date`                                                      | String        | Optional    | Planned or actual start date of the treatment, in `YYYY-MM-DD` format                                                                                                                         |  
| `isStarted`                                                           | Boolean       | Required    | Whether the treatment has been started                                                                                                                                                        |  
| `appliedTax`                                                          | Array[object] | Optional    | List of taxes applied to this treatment plan                                                                                                                                                  |  
| `appliedTax[].taxId`                                                  | UUID          | Required    | Unique identifier of the tax                                                                                                                                                                  |  
| `appliedTax[].name`                                                   | String        | Required    | Display name of the tax (e.g. `VAT`)                                                                                                                                                          |  
| `appliedTax[].percentage`                                             | Float         | Required    | Tax rate as a percentage                                                                                                                                                                      |  
| `appliedTax[].amount`                                                 | Float         | Required    | Calculated tax amount                                                                                                                                                                         |  
| `paymentDetails`                                                      | Object        | Required    | Pricing and payment breakdown for the treatment                                                                                                                                               |  
| `paymentDetails.rate`                                                 | Float         | Required    | Unit price of the treatment                                                                                                                                                                   |  
| `paymentDetails.quantity`                                             | Float         | Required    | Quantity of units applied                                                                                                                                                                     |  
| `paymentDetails.currency`                                             | String        | Required    | Currency code for the amounts (e.g. `AED`)                                                                                                                                                    |  
| `paymentDetails.total`                                                | Float         | Required    | Total price before tax, discount, and insurance adjustments                                                                                                                                   |  
| `paymentDetails.discount`                                             | Float         | Optional    | Discount amount applied to the treatment                                                                                                                                                      |  
| `paymentDetails.insured`                                              | Float         | Optional    | Portion of the total covered by insurance                                                                                                                                                     |  
| `paymentDetails.tax`                                                  | Float         | Optional    | Total tax amount applied, matching the sum of `appliedTax[].amount`                                                                                                                           |  
| `startTime.milliSeconds`                                              | Long          | Optional    | Timestamp (epoch milliseconds) of the treatment's scheduled or actual start time                                                                                                              |