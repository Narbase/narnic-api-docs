---
sidebar_position: 2
---
# Get Appointments List (Search)
## Request
URL:  `<BASE_URL>/api/user/v1/appointments/search` ; Note: (use `/search` instead of `/list`)

VERB: `POST`  

Authentication: Bearer token  

Body:  
```json
{  
  "pageNo": 0,  
  "pageSize": 20,  
  "searchTerm": "",  
  "doctors": [  
    "UUID"  
  ],  
  "includedStatus": [  
    "Started"  
  ],  
  "rangeStart": {
          "milliSeconds": 1708772400000
  },  
  "rangeEnd": {
          "milliSeconds": 1708772400000
   },  
  "isMySchedule": false,  
  "getAddressedTreatments": false,  
  "patientId": null  
}
```

### Description:  
This endpoint allows searching for appointments with various filtering options. It supports pagination and can filter by doctor, status, date range, and patient.

| Parameter                | Is required | Description                                                                                                                                             |
| ------------------------ | ----------- | ------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `pageNo`                 | Required    | The page number for paginated results (0-based index). Default: 0                                                                                       |
| `pageSize`               | Required    | The number of items per page. Default: 20                                                                                                               |
| `searchTerm`             | Required    | A search term to filter appointments (searches in patient details etc.). Leave empty to get all appointments                                            |
| `doctors`                | Required    | Array of doctor UUIDs to filter appointments by specific doctors                                                                                        |
| `includedStatus`         | Required    | Array of status values to include in results Should be in ("Unconfirmed", "Scheduled", "PatientArrived", "Started", "Completed", "Cancelled", "NoShow") |
| `rangeStart`             | Optional    | Start timestamp (in milliseconds) for date range filtering. Null means no start limit                                                                   |
| `rangeEnd`               | Optional    | End timestamp (in milliseconds) for date range filtering. Null means no end limit                                                                       |
| `isMySchedule`           | Required    | Should be `false` always                                                                                                                                |
| `getAddressedTreatments` | Required    | Should be `false` always                                                                                                                                |
| `patientId`              | Optional    | Patient UUID to filter appointments for a specific patient. Null means all patients                                                                     |

## Response  
```json
{
  "data": {
    "list": [
      {
        "id": "UUID",
        "patient": "<SimplePatientDto>",
        "doctorId": "UUID",
        "doctorName": {
          "title": "Dr.",
          "preferredName": "Doctor preferred name",
          "fullName": "Doctor name"
        },
        "doctorColor": "279d9d",
        "plannedStartTime": {
          "milliSeconds": 1708771500000
        },
        "plannedEndTime": {
          "milliSeconds": 1708772400000
        },
        "visitType": {
          "name": "Cleaning",
          "color": "000000",
          "durationInMinutes": 15
        },
        "status": "Started",
        "notes": "Appointment notes",
        "createdOn": {
          "milliSeconds": 1691321000008
        },
        "addressedTreatments": [],
        "invoiceItem": "<InvoiceItemDto>"
      }
    ],
    "total": 171
  },
  "status": "0"
}
```

### Response Description:  
- `data.list`: Array of appointment objects matching the search criteria  
- `data.total`: Total number of appointments matching the filters (regardless of pagination)  
- `status`: Status code indicating success ("0") or error  

#### Appointment Object Fields:  
- `id`: Unique identifier for the appointment  
- `patient`: [SimplePatientDto](/common-dtos/simple-patient-dto) object 
- `doctorId`: Unique identifier of the attending doctor  
- `doctorName`: Object containing doctor's title and name information  
- `doctorColor`: Color code associated with the doctor  
- `plannedStartTime`: Scheduled start time in milliseconds since epoch  
- `plannedEndTime`: Scheduled end time in milliseconds since epoch  
- `visitType`: Details about the appointment type (name, color, duration)  
- `status`: Current status of the appointment  
- `notes`: Any notes associated with the appointment  
- `createdOn`: When the appointment was created  
- `addressedTreatments`: List of treatments addressed in this appointment  
- `invoiceItem`: [InvoiceItemDto](/common-dtos/invoice-item-dto) object

