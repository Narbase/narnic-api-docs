---
sidebar_position: 3
---
# Get Patients List
## Request  
URL:  `<BASE_URL>/api/user/v1/patients/list`  

VERB: `POST`  

Authentication: Bearer token  

Body:  
```json
{  
  "pageNo": 0,  
  "pageSize": 20,  
  "searchTerm": "",  
  "filters": {  
    "gender": "Male",  
    "maxDateOfBirth": null,  
    "minDateOfBirth": {  
      "date": "2005-06-26"  
    },  
    "outstandingPatients": false  
  }  
}
```

### Description:  
Retrieves a paginated list of patients based on optional search criteria and filters.  

| Parameter                     | Is Required | Description                                                                                                                |
| ----------------------------- | ----------- | -------------------------------------------------------------------------------------------------------------------------- |
| `pageNo`                      | Required    | The page number to fetch (0-based index).                                                                                  |
| `pageSize`                    | Required    | The number of records to return per page.                                                                                  |
| `searchTerm`                  | Required    | A search term to filter patients by name, patient number, or other relevant fields. Send empty string to disable searching |
| `filters`                     | Optional    | Additional filters to narrow down the patient list.                                                                        |
| `filters.gender`              | Optional    | Filter patients by gender (e.g., `"Male"`, `"Female"`).                                                                    |
| `filters.maxDateOfBirth`      | Optional    | The maximum date of birth (inclusive) for filtering patients. Format: `{ "date": "YYYY-MM-DD" }` or `null` for no filter.  |
| `filters.minDateOfBirth`      | Optional    | The minimum date of birth (inclusive) for filtering patients. Format: `{ "date": "YYYY-MM-DD" }` or `null` for no filter.  |
| `filters.outstandingPatients` | Optional    | If `true`, only returns patients with outstanding payments. Default: `false`.                                              |

## Response  
```json
{  
  "data": {  
    "list": [  
      <FullPatientDto>
    ],  
    "total": 100  
  },  
  "status": "0"  
}
```

### Response Fields:  
| Field              | Description                                                                 |
| ------------------ | --------------------------------------------------------------------------- |
| `data.list`        | An array of patient objects matching the request criteria.                  |
| `data.total`       | The total number of patients available (before pagination).                 |
| `status`           | Indicates the response status (`"0"` for success, other values for errors). |
| **Patient Object** | [Full Patient Dto](/common-dtos/full-patient-dto)                           |

