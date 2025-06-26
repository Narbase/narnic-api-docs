---
sidebar_position: 3
---
# Inovice Item DTO

Used for invoicing
## Structure
```json
{  
  "id": "UUID",  
  "clinicId": "UUID",  
  "createdOn": {  
    "milliSeconds": 1691321000008  
  },  
  "invoiceId": "UUID",  
  "name": "Item name",  
  "description": "",  
  "type": "Visit",  
  "insuranceOffer": {  
    "contractedFees": 0.0,  
    "copay": 0.0,  
    "coverage": 100.0,  
    "fixedCoverage": 0.0,  
    "currency": "AED"  
  },  
  "appliedTax": [],  
  "paymentDetails": {  
    "currency": "AED",  
    "total": 0.0,  
    "discount": 0.0,  
    "insured": 0.0,  
    "tax": 0.0  
  },  
  "referencePayment": {  
    "currency": "AED",  
    "amount": 0.0  
  },  
  "insurancePlanId": "UUID",  
  "appointmentId": "UUID",  
  "insuranceClaimId": "UUID",  
  "notes": ""  
}
```


| Parameter          | Type   | Description                                                                 |
| ------------------ | ------ | --------------------------------------------------------------------------- |
| `id`               | UUID   | Unique identifier for the invoice item                                      |
| `clinicId`         | UUID   | Unique identifier of the clinic associated with the invoice item            |
| `createdOn`        | Object | Timestamp when the invoice item was created (in milliseconds since epoch)   |
| `invoiceId`        | UUID   | Unique identifier of the invoice this item belongs to                       |
| `name`             | String | Display name of the invoice item (e.g., service name with provider details) |
| `description`      | String | Additional description of the invoice item (empty in this example)          |
| `type`             | String | Can be Visit, Treatment, or Additional                                      |
| `insuranceOffer`   | Object | Insurance coverage details for this item:                                   |
| ↳ `contractedFees` | Float  | Contractually agreed fees between clinic and insurer                        |
| ↳ `copay`          | Float  | Patient's copayment amount                                                  |
| ↳ `coverage`       | Float  | Percentage of costs covered by insurance                                    |
| ↳ `fixedCoverage`  | Float  | Fixed amount covered by insurance (alternative to percentage)               |
| ↳ `currency`       | String | Currency used for all monetary values (AED in this example)                 |
| `appliedTax`       | Array  | List of taxes applied to this item (empty in this example)                  |
| `paymentDetails`   | Object | Financial details for this item:                                            |
| ↳ `currency`       | String | Currency used (AED in this example)                                         |
| ↳ `total`          | Float  | Total amount for this item                                                  |
| ↳ `discount`       | Float  | Discount amount applied                                                     |
| ↳ `insured`        | Float  | Amount covered by insurance                                                 |
| ↳ `tax`            | Float  | Tax amount applied                                                          |
| `referencePayment` | Object | Reference payment information:                                              |
| ↳ `currency`       | String | Currency used (AED in this example)                                         |
| ↳ `amount`         | Float  | Reference payment amount                                                    |
| `insurancePlanId`  | UUID   | Unique identifier of the insurance plan associated with this item           |
| `appointmentId`    | UUID   | Unique identifier of the appointment associated with this item              |
| `insuranceClaimId` | UUID   | Unique identifier of the insurance claim associated with this item          |
| `notes`            | String | Additional notes about the invoice item (empty in this example)             |