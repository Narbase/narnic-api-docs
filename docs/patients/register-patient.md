---
sidebar_position: 2
---
# Register Patient
## Request
URL:  `<BASE_URL>/api/user/v1/patients/add`
VERB: `POST`
Authentication: Bearer token
Body:
```json
{  
  "isLead": true,  
  "preferredName": "Incomplete patient",  
  "fullName": "Incomplete patient ",  
  "callingCode": "+971",  
  "localPhone": "",  
  "email": null,  
  "gender": "Male",  
  "dateOfBirth": {  
    "date": "1111-01-01"  
  }  
}
```

Description:

| Parameter          | Is required | Description                                                                                                                  |
| ------------------ | ----------- | ---------------------------------------------------------------------------------------------------------------------------- |
| `isLead`           | Required    | Should be true to prevent server side verification for required data                                                         |
| preferredName      | Required    | Patient preferred name. Used to personal communication. Can be set the same as fullName. Can be empty if `isLead` is `true`. |
| `fullName`         | Required    | Patient full name. Can be empty if `isLead` is `true`.                                                                       |
| `callingCode`      | Required    | Patient calling code. e.g. +971. Can be empty if `isLead` is `true`.                                                         |
| `localPhone`       | Required    | Patient phone. e.g. 561231231. Can be empty if `isLead` is `true`.                                                           |
| `email`            | Optional    | Patient email                                                                                                                |
| `gender`           | Required    | Should be `Male` or `Female`. Always required.                                                                               |
| `dateOfBirth.date` | Required    | Formatted `YYYY-MM-DD`. Always required. Send `1111-01-01` when `isLead` is true.                                            |


## Response
```json
{  
  "data": {  
    "patient": {  
      "id": "0d004909-7a04-4909-8c7f-xxxxxxxxxxxx",  
      "clinicId": "50dbdfc3-0155-424a-8c55-xxxxxxxxxxxx",  
      "patientNo": "-1",  
      "fullName": "Incomplete patient ",  
      "preferredName": "Incomplete patient",  
      "callingCode": "+971",  
      "localPhone": "",  
      "gender": "Male",  
      "dateOfBirth": {  
        "date": "1111-01-01"  
      },  
      "email": "",  
      "additionalInfo": [],  
      "insuranceInfo": []  
    }  
  },  
  "status": "0"  
}
```
