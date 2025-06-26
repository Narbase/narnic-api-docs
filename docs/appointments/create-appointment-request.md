---
sidebar_position: 2
---
# Create Appointment Request
## Request
URL:  `<BASE_URL>/api/v1/appointments/requests/create`

VERB: `POST`

Authentication: Bearer token

Body:
```json
{
  "createRequest" : {
    "externalId": "Externally Generated ID",
    "type": "New",
    "data": {
      "newAppointmentData": {
        "patientName": "Optional: Patient name",
        "patientCallingCode": "Optional: Patient calling code. e.g. +971",
        "patientLocalPhone":  "Optional: Patient phone. e.g. 561231231",
        "doctorId": "Optional: Doctor ID in Medico",
        "startTime": {
          "milliSeconds": 1726492349955
        },
        "endTime": {
          "milliSeconds": 1726492449955
        },
        "notes":  "Optional: any notes from patient"
      }
    }
  }
}
```

Description:

| Parameter            | Is required | Description                                                                                                      |
| -------------------- | ----------- | ---------------------------------------------------------------------------------------------------------------- |
| `externalId`         | Required    | Externally generated ID - Should be unique for each request                                                      |
| `type`               | Required    | Should be `New` For new appointment requests                                                                     |
| `data`               | Required    | New appointment request data                                                                                     |
| `patientName`        | Optional    | Patient name                                                                                                     |
| `patientCallingCode` | Optional    | Patient calling code. e.g. +971                                                                                  |
| `patientLocalPhone`  | Optional    | Patient phone. e.g. 561231231                                                                                    |
| `doctorId`           | Optional    | Doctor ID in Medico                                                                                              |
| `startTime`          | Required    | The field `milliSeconds` is a Long shows the epoch time for the patient preferred start time for the appointment |
| `endTime`            | Required    | The field `milliSeconds` is a Long shows the epoch time for the patient preferred end time for the appointment   |
| `notes`              | Optional    | Any notes from patient                                                                                           |

## Response

```json
{  
  "status": "0"  
}
```

