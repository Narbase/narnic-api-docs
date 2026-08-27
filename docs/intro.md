---
sidebar_position: 1
slug: /
---
# Narnic API Documentation

Narnic API Technical Documentation


All requests uses `https://app.balsammedico.com/` as `BASE_URL`



## Registering An App in Balsam Medico
For integration, you will need to create an App in the admin area in Balsam Medico. This is will allow you to generate an authentication token for the app and to listen to the webhook from Balsam Medico. (Admin page > Apps > Add new)

1. What types of API endpoints are available?
These docs shows the most commonly used API endpoints
Please note that not all the API are there (but cover most common cases). Please let us know if you need some specific functionality.

2. What authentication methods are supported?
JWT and OAuth flow. You can generate a JWT for your app in the admin area in Balsam Medico.

3. Is there a sandbox or test environment available for integration testing?
You can create a testing account at https://app.balsammedico.com/trial

4. Does the system support Webhooks or Event Notifications?
Yes. You can find the supported webhooks in the admin app config page.

5. What should the value of Extension Point be?
The Extension Point is where you will be receiving the webhook callback. If you do not want to receive the webhook callbacks, please set it to https://app.balsammedico.com/api/public/app/v1/sink and untick all webhooks in the configuration dialog.
Currently, the system support the following webhooks:

```
Auth.Token
Clinics.InsuranceClaimsProcessor
Clinics.SettingsPage
Scheduling.VisitStatus
Scheduling.VisitCreated
Scheduling.VisitUpdate
Patients.RegistrationInfo
Patients.PatientAdded
Patients.PatientUpdated
Patients.GetPatientInfo
Patients.PatientMerged
Patients.PatientsListOptions
Patients.NextOfKinUpserted
Patients.NextOfKinDeleted
Emr.TreatmentPlanUpdated
Emr.HistoryUpdated
Emr.VitalsLogEntryAdded
Emr.VitalsLogEntryEdited
Emr.PrescriptionGenerated
Emr.PrescriptionRevoked
Emr.PatientAllergyUpdated
Emr.PatientAllergyDeleted
Emr.PatientProblemUpdated
Emr.PatientProblemDeleted
Emr.PatientDiagnosisUpdated
Emr.PatientDiagnosisDeleted
Emr.PatientFilesUpdated
Emr.GetCurrentVisitOptions
Emr.PatientSocialHistoryUpdated
Emr.PatientSocialHistoryDeleted
Emr.PatientFamilyHistoryUpdated
Emr.PatientFamilyHistoryDeleted
Emr.PatientDiagnosticUpdated
Emr.PatientDiagnosticDeleted
StaffRegistrationInfo.StaffAdded
StaffRegistrationInfo.StaffUpdated
StaffRegistrationInfo.GetStaffInfo
Forms.GetFormsTemplates
Insurance.ClaimOptions
AppointmentRequest.ChangeAppointmentRequestStatus
```