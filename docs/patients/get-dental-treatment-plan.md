---
sidebar_position: 2
---
# Get Dental Treatment Plan 
## Request
URL:  `<BASE_URL>/api/v1/emr/dental_practice_emr/get_or_create`

VERB: `POST`

Authentication: Bearer token

Body:
```json
{
    "patientId": "UUID"
}
```

Description:

| Parameter   | Is required | Description |
| ----------- | ----------- | ----------- |
| `patientId` | Required    | Patient ID  |



## Response
```json
{  
  "data": {  
    "practiceEmrId": "d34b4f0c-6ae2-42ac-9baf-xxxxxxxxxxxx",  
    "notes": "",  
    "treatments": [  
      {  
        "treatment": <Dental Treatment Dto>,  
        "template": <Treatment Template DTO>,  
        "staff": {  
          "clientId": "UUID",  
          "staffId": "UUID",  
          "preferredName": "Abdallah",  
          "fullName": "Abdallah Mohammed Osman",  
          "doctorDto": {  
            "doctorId": "11d05066-92ac-4b82-8825-xxxxxxxxxxxx",  
            "title": "Dr.",  
            "color": "4d42bd"  
          }  
        },  
        "diagnoses": [  
          {  
            "id": "f0ad16e2-0162-4ba0-923e-xxxxxxxxxxxx",  
            "name": "Arrested dental caries",  
            "description": "Arrested dental caries",  
            "code": "K02.3",  
            "standard": "Icd10cm2018"  
          }  
        ]  
      }  
    ],  
    "conditions": [  
      {  
        "uiId": "69f5f160-c26b-43d5-8d28-xxxxxxxxxxxx",  
        "name": "Caries",  
        "code": "CariesAdvanced",  
        "toothNumber": 11,  
        "tooth": {  
          "toothOrder": 11,  
          "isPrimary": false,  
          "isSupernumerary": false  
        },  
        "data": {  
          "entries": [  
            {  
              "surface": "Buccal",  
              "severity": 3  
            },  
            {  
              "surface": "Lingual",  
              "severity": 1  
            },  
            {  
              "surface": "Distal",  
              "severity": 3  
            }  
          ]  
        },  
        "createdOn": {  
          "milliSeconds": 1784550840000  
        }  
      }]  
  },  
  "status": "0"  
}
```

### Response Fields:  
| Field                                | Description                                                                 |
| ------------------------------------ | --------------------------------------------------------------------------- |
| `data.treatments[].treatment` object | [Dental Treatment DTO](/common-dtos/dental-treatment-dto)                   |
| `data.treatments[].template` object  | [Treatment Template DTO](/common-dtos/treatment-template-dto)               |
| `status`                             | Indicates the response status (`"0"` for success, other values for errors). |
