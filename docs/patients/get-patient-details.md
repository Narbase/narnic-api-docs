---
sidebar_position: 4
---
# Get Patient Details
## Request  
URL:  `<BASE_URL>/api/user/v1/patient_details`  

VERB: `POST`  

Authentication: Bearer token  

Body:  
```json
{  
  "patientId": "UUID"
}
```

### Description:  
Retrieves a single patient details.

| Parameter                     | Is Required | Description    |
| ----------------------------- | ----------- | -------------- |
| `patientId`                   | Required    | The patient ID |


## Response  
```json
{  
  "data": {  
    "patient": <FullPatientDto>
  },  
  "status": "0"  
}
```

### Response Fields:  
| Field                 | Description                                                                 |
| --------------------- | --------------------------------------------------------------------------- |
| `data.patient` object | [Full Patient Dto](/common-dtos/full-patient-dto)                           |
| `status`              | Indicates the response status (`"0"` for success, other values for errors). |


