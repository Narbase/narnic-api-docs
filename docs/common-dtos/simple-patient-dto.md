---
sidebar_position: 1
---
# Simple Patient DTO

Simplified Patient DTO; normally used for display.

## Structure
```json
{
	"id": "UUID",
	"patientNo": Int,
	"preferredName": "String",
	"fullName": "String",
	"dateOfBirth": {
	"date": "1999-01-01"
	},
	"callingCode": "+971",
	"localPhone": "00000000",
	"email": "email",
	"alerts": "Patient alerts"
}
```

| Parameter          | Type    | Is required | Description                                                                                           |
| ------------------ | ------- | ----------- | ----------------------------------------------------------------------------------------------------- |
| `id`               | UUID    | Required    | Unique identifier for the patient record                                                              |
| `patientNo`        | Integer | Required    | Patient identification number. -1 if patient is a lead.                                               |
| `preferredName`    | String  | Required    | The name the patient prefers to be called by. Or Patient First name if the clinic is using Split name |
| `fullName`         | String  | Required    | The patient's complete legal name Or "FirstName LastName"  if the clinic is using Split name          |
| `dateOfBirth.date` | String  | Required    | The patient's birth date in YYYY-MM-DD format. It will be '1111-01-01' if not available.              |
| `callingCode`      | String  | Required    | International dialing code for the patient's phone number (e.g., +971)                                |
| `localPhone`       | String  | Required    | The local portion of the patient's phone number                                                       |
| `email`            | String  | Optional    | The patient's email address                                                                           |
| `alerts`           | String  | Optional    | Important notifications or warnings about the patient (e.g., allergies, special needs)                |
