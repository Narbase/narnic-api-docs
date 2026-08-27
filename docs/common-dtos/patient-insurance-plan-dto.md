---
sidebar_position: 7
---
# Patient Insurance Plan DTO

Represents an insurance plan associated with a patient, including the provider and insurance card details.

## Structure

```json
{
  "planId": "UUID",
  "planName": "String",
  "providerName": "String",
  "cardInfo": {
    "cardNumber": "String",
    "cardExpirationDate": {
      "date": "2026-07-21"
    }
  }
}
```

## Fields

|Parameter|Type|Is required|Description|
|---|---|---|---|
|`planId`|UUID|Required|Unique identifier for the insurance plan|
|`planName`|String|Required|Name of the insurance plan (e.g. `salama 50%`)|
|`providerName`|String|Required|Name of the insurance provider/company (e.g. `tameenat`)|
|`cardInfo`|Object|Optional|Details of the patient's insurance card|
|`cardInfo.cardNumber`|String|Optional|Insurance card number|
|`cardInfo.cardExpirationDate.date`|String|Optional|Expiration date of the insurance card, in `YYYY-MM-DD` format|