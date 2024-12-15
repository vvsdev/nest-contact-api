# Address API Specs

## Create Address

**Method**: POST

**Endpoint**: `/api/contacts/:contactId/addresses`

**Headers**:
- `Authorization: Bearer <token>`

**Request Body**:

```json
{
    "street": "Jln. Presiden Mulyono",
    "city": "Kota Wakanda",
    "province": "Provinsi Siganshina",
    "country": "Negara Konoha",
    "postal_code": "163524"
}
```

**Response Body (Success)**:

**Status Code**: `201 Created`

```json
{
    "data": {
        "id": 1,
        "street": "Jln. Presiden Mulyono",
        "city": "Kota Wakanda",
        "province": "Provinsi Siganshina",
        "country": "Negara Konoha",
        "postal_code": "163524"
    }
}
```

**Response Body (Failed)**:

**Status Code**: `401 Unauthorized`

```json
{
    "error_code": "UNAUTHORIZED",
    "message": "Access denied. Please provide a valid Bearer token."
}
```

## Update Address

**Method**: PUT

**Endpoint**: `/api/contacts/:contactId/addresses/:addressId`

**Headers**:
- `Authorization: Bearer <token>`

**Request Body**:

```json
{
    "street": "Jln. Presiden Mulyono",
    "city": "Kota Wakanda",
    "province": "Provinsi Siganshina",
    "country": "Negara Konoha",
    "postal_code": "163524"
}
```

**Response Body (Success)**:

**Status Code**: `200 OK`

```json
{
    "data": {
        "id": 1,
        "street": "Jln. Presiden Mulyono",
        "city": "Kota Wakanda",
        "province": "Provinsi Siganshina",
        "country": "Negara Konoha",
        "postal_code": "163524"
    }
}
```

**Response Body (Failed)**:

**Status Code**: `401 Unauthorized`

```json
{
    "error_code": "INVALID_CREDENTIALS",
    "message": "Access denied. Please provide a valid Bearer token."
}
```

## Get Address

**Method**: GET

**Endpoint**: `/api/contacts/:contactId/addresses/:addressId`

**Headers**:
- `Authorization: Bearer <token>`

**Response Body (Success)**:

**Status Code**: `200 OK`

```json
{
    "data": {
        "id": 1,
        "street": "Jln. Presiden Mulyono",
        "city": "Kota Wakanda",
        "province": "Provinsi Siganshina",
        "country": "Negara Konoha",
        "postal_code": "163524"
    }
}
```

**Response Body (Failed)**:

**Status Code**: `401 Unauthorized`

```json
{
    "error_code": "UNAUTHORIZED",
    "message": "Access denied. Please provide a valid Bearer token."
}
```

## Get List Addresses

**Method**: GET

**Endpoint**: `/api/contacts/:contactId/addresses`

**Headers**:
- `Authorization: Bearer <token>`

**Response Body (Success)**:

**Status Code**: `200 OK`

```json
{
    "data": [
        {
            "id": 1,
            "street": "Jln. Presiden Mulyono",
            "city": "Kota Wakanda",
            "province": "Provinsi Siganshina",
            "country": "Negara Konoha",
            "postal_code": "163524"
        },
        {
            "id": 2,
            "street": "Jln. Presiden Mulyono",
            "city": "Kota Wakanda",
            "province": "Provinsi Siganshina",
            "country": "Negara Konoha",
            "postal_code": "163524"
        }
    ]
}
```

**Response Body (Failed)**:

**Status Code**: `401 Unauthorized`

```json
{
    "error_code": "UNAUTHORIZED",
    "message": "Access denied. Please provide a valid Bearer token."
}
```

## Remove Contact

**Method**: DELETE

**Endpoint**: `/api/contacts/:contactId/addresses/:addressId`

**Headers**:
- `Authorization: Bearer <token>`

**Response Body (Success)**:

**Status Code**: `200 OK`

```json
{
    "data": {
        "message": "Data deleted successfuly",
    }
}
```

**Response Body (Failed)**:

**Status Code**: `401 Unauthorized`

```json
{
    "error_code": "UNAUTHORIZED",
    "message": "Access denied. Please provide a valid Bearer token."
}
```