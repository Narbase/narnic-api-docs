---
sidebar_position: 2
---
# Full Patient DTO

Full Patient DTO

## Structure
```json
{  
	"id": "UUID",  
	"clinicId": "UUID",  
	"chainId": "UUID",  
	"patientNo": "24160",  
	"profilePhotoUrl": "/files/cardholder.jpg.820x500_crop.jpeg",  
	"fullName": "Patient full name",  
	"preferredName": "Patient preferred name",  
	"callingCode": "+971",  
	"localPhone": "1111111111",  
	"gender": "Male",  
	"dateOfBirth": {  
	  "date": "1970-07-01"  
	},  
	"email": "",  
	"additionalInfo": [],  
	"insuranceInfo": [],  
	"outstandingPayments": [
		{
		"currency": "AED",
		"amount": 0.0
	  }
	]  
}
```


| Field                 | Description                                                   |
| --------------------- | ------------------------------------------------------------- |
| `id`                  | Unique identifier for the patient.                            |
| `clinicId`            | Unique identifier for the clinic associated with the patient. |
| `chainId`             | Unique identifier for the chain (if applicable).              |
| `patientNo`           | Patient's assigned identification number.                     |
| `profilePhotoUrl`     | URL of the patient's profile photo (if available).            |
| `fullName`            | The patient's full legal name.                                |
| `preferredName`       | The patient's preferred name (if specified).                  |
| `callingCode`         | The country calling code for the patient's phone number.      |
| `localPhone`          | The patient's phone number (without calling code).            |
| `gender`              | The patient's gender (`"Male"`, `"Female"`, etc.).            |
| `dateOfBirth.date`    | The patient's date of birth in `YYYY-MM-DD` format.           |
| `email`               | The patient's email address (if available).                   |
| `additionalInfo`      | Additional custom fields (specific to the clinic).            |
| `insuranceInfo`       | Insurance-related details (if available).                     |
| `outstandingPayments` | List of pending payments (if applicable).                     |
