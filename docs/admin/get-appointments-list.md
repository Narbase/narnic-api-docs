---
sidebar_position: 2
---
# Get Treatments Templates List with prices
## Request
URL:  `<BASE_URL>/api/admin/v1/settings/treatments/templates/list`

VERB: `POST`

Authentication: Bearer token

Body:
```json
{
  "pageNo": 0,
  "pageSize": 20,
  "searchTerm": ""
}
```

### Description:
This endpoint retrieves a paginated list of treatment templates with optional search functionality. The response includes treatment details such as name (in both English and Arabic), type, code, group, currency, and price.

| Parameter                | Is required | Description                                                                                                                                             |
| ------------------------ | ----------- | ------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `pageNo`                 | Required    | The page number for paginated results (0-based index). Default: 0                                                                                       |
| `pageSize`               | Required    | The number of items per page. Default: 20                                                                                                               |
| `searchTerm`             | Required    | A search term to filter appointments (searches in patient details etc.). Leave empty to get all appointments                                            |

## Response
```json
{
  "data": {
    "list": [
      {
        "id": "UUID",
        "name": {
          "en": "Maryland Bridge",
          "ar": "Maryland Bridge"
        },
        "type": "Treatment group",
        "code": "CDT or clinic code",
        "group": "Treatment group",
        "currency": "AED",
        "price": 4000.0
      }
    ],
    "total": 100
  },
  "status": "0"
}
```

### Response Description:
The response contains a paginated list of treatment templates and the total count of available templates.

| Field               | Description                                                                                                                  |
| ------------------- | ---------------------------------------------------------------------------------------------------------------------------- |
| `data.list`         | Array of treatment template objects                                                                                          |
| `data.total`        | Total number of treatment templates available (not just in current page)                                                     |
| `status`            | Status code indicating success ("0") or error                                                                                |

**Template Details**

| Field               | Description                                                                                                                  |
| ------------------- | ---------------------------------------------------------------------------------------------------------------------------- |
| `id`    | Unique identifier for the treatment template                                                                                 |
| `name`  | Object containing the treatment name in English (`en`) and Arabic (`ar`)                                                     |
| `type`  | The type/category of the treatment                                                                                           |
| `code`  | The procedure code (either CDT code or clinic-specific code)                                                                 |
| `group` | The group this treatment belongs to                                                                                          |
| `currency` | The currency for the treatment price                                                                                      |
| `price` | The cost of the treatment
