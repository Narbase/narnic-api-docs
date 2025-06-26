---
sidebar_position: 2
---
# Get Clinic Settings List
## Request
URL: `<BASE_URL>/api/user/v1/clinic_settings/list`

VERB: `POST`

Authentication: Bearer token

Body: `None`

### Description:
This endpoint retrieves a list of clinic settings, including working hours, default configurations, practice settings, and operating rules. No request parameters are required.

## Response
```json
{
  "data": {
    "list": [
      {
        "defaultCallingNumber": "+971",
        "firstDayOfTheWeek": "SAT",
        "workingHours": {
          "days": [
            {
              "dayDto": "SUN",
              "startTime": "11:00:00",
              "endTime": "20:00:00"
            }
          ]
        },
        "clinicSettings": {
          "defaultCurrency": "AED",
          "currencies": [
            "AED"
          ],
          "diagnosisStandard": "Icd10cm2018",
          "languages": [
            "en-GB"
          ],
          "doctorsIdsOrdered": [
            "UUID"
          ],
          "doctorsIdsHidden": [
            "UUID"
          ],
          "use12Hours": true,
          "usePatientSplitNames": true,
          "preventStartingVisitWhenPatientHasNotArrived": true,
          "patientNoPrefix": "",
          "enableCreditNotesComponent": true
        },
        "clinicTimeZone": "Asia/Dubai",
        "operatingSettings": {
          "lockCompletedAppointment": true,
          "maxBeforeMinutesBeforeAppointmentStart": 180
        }
      }
    ]
  },
  "status": "0"
}
```

### Response Parameters

| Parameter | Description |
| --------- | ----------- |
| `data.list.defaultCallingNumber` | Default country calling code for phone numbers. |
| `data.list.firstDayOfTheWeek` | The first day of the week (e.g., `SAT`). |
| `data.list.workingHours.days` | List of clinic working days with start and end times. |
| `data.list.clinicSettings.defaultCurrency` | Default currency used in the clinic (e.g., `AED`). |
| `data.list.clinicSettings.currencies` | List of supported currencies. |
| `data.list.clinicSettings.diagnosisStandard` | Standard used for diagnosis (e.g., `Icd10cm2018`). |
| `data.list.clinicSettings.languages` | Supported languages (e.g., `en-GB`). |
| `data.list.clinicSettings.doctorsIdsOrdered` | Ordered list of doctor IDs for display. |
| `data.list.clinicSettings.doctorsIdsHidden` | List of hidden doctor IDs. |
| `data.list.clinicSettings.use12Hours` | Whether the clinic uses 12-hour time format. |
| `data.list.clinicSettings.usePatientSplitNames` | Whether patient names are split into first/last. |
| `data.list.clinicSettings.preventStartingVisitWhenPatientHasNotArrived` | Restricts visit start unless patient has arrived. |
| `data.list.clinicSettings.patientNoPrefix` | Prefix for patient numbers (if applicable). |
| `data.list.clinicSettings.enableCreditNotesComponent` | Whether credit notes are enabled. |
| `data.list.clinicTimeZone` | Timezone of the clinic (e.g., `Asia/Dubai`). |
| `data.list.operatingSettings.lockCompletedAppointment` | Whether completed appointments are locked. |
| `data.list.operatingSettings.maxBeforeMinutesBeforeAppointmentStart` | Allowed early check-in time (in minutes). |
| `data.list.id` | Unique ID of the clinic settings record. |
| `status` | Response status code (`0` for success). |

---
