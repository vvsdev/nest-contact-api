# Contact API Specs

## Create Contact

**Method**: POST

**Endpoint**: `/api/contacts`

**Headers**:
- `Authorization: Bearer <token>`

**Request Body**:

```json
{
    "first_name": "Joko",
    "last_name": "Widodo",
    "email": "jokowi@gmail.com",
    "phone": "098767872661"
}
```

**Response Body (Success)**:

**Status Code**: `201 Created`

```json
{
    "data": {
        "id": 1,
        "first_name": "Joko",
        "last_name": "Widodo",
        "email": "jokowi@gmail.com",
        "phone": "098767872661"
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

## Update Contact

**Method**: PUT

**Endpoint**: `/api/contacts/:contactId`

**Headers**:
- `Authorization: Bearer <token>`

**Request Body**:

```json
{
    "first_name": "Joko",
    "last_name": "Widodo",
    "email": "jokowi@gmail.com",
    "phone": "098767872661"
}
```

**Response Body (Success)**:

**Status Code**: `200 OK`

```json
{
    "data": {
        "id": 1,
        "first_name": "Joko",
        "last_name": "Widodo",
        "email": "jokowi@gmail.com",
        "phone": "098767872661"
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

## Get Contact

**Method**: GET

**Endpoint**: `/api/contacts/:contactId`

**Headers**:
- `Authorization: Bearer <token>`

**Response Body (Success)**:

**Status Code**: `200 OK`

```json
{
    "data": {
        "id": 1,
        "first_name": "Joko",
        "last_name": "Widodo",
        "email": "jokowi@gmail.com",
        "phone": "098767872661"
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

## Remove Contact

**Method**: DELETE

**Endpoint**: `/api/contacts/:contactId`

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

## Search Contact

**Method**: GET

**Endpoint**: `/api/contacts`

**Headers**:
- `Authorization: Bearer <token>`

**Query Params**:
- `name: string, search first name or last name`
- `email: string, search email`
- `phone: string, search phone number`
- `page: number, default 1`
- `size: number, default 10`

**Response Body (Success)**:

**Status Code**: `200 OK`

```json
{
    "data": [
        {
            "id": 1,
            "first_name": "Joko",
            "last_name": "Widodo",
            "email": "jokowi@gmail.com",
            "phone": "098767872661"
        },
        {
            "id": 2,
            "first_name": "Gibren",
            "last_name": "Rakabuming",
            "email": "fufufafa@gmail.com",
            "phone": "098767872666"
        }
    ],
    "paging": {
        "current_page": 1,
        "total_size": 10,
        "size": 10
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