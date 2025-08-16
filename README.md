---

# API Documentation

## Base URL:

```
http://10.10.12.54:3000/api/v1
```

---

## Endpoints

### 1. **Create User**

**Method**: `POST`
**Endpoint**: `/user/create-user`
**Description**: Creates a new user with data and an image file.

#### Input (FormData):

- `name` (String): Full name of the user.
- `email` (String): User's email address.
- `password` (String): User's password.
- `image` (File): User's profile image.

#### Output:

```json
{
  "success": true,
  "message": "Please check your email to verify your account."
}
```

---

### 2. **Email Verification**

**Method**: `POST`
**Endpoint**: `/auth/verify-email`
**Description**: Verifies the user's email address using a one-time code.

#### Input:

```json
{
  "email": "johndoe@example.com",
  "oneTimeCode": 741603
}
```

#### Output:

```json
{
  "success": true,
  "message": "Your email has been successfully verified. Your account is now fully activated.",
  "data": {
    "accessToken": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6IjY4YTAxNDQzMmVmNjE1Mjc5YmMyMmQwOSIsInJvbGUiOiJVU0VSIiwiZW1haWwiOiJqb2huZG9lQGV4YW1wbGUuY29tIiwiaWF0IjoxNzU1MzIxNzMxLCJleHAiOjE3NTc5MTM3MzF9.xvhzvY32T3f5wdTeB2bSb8KZAgA0BWYgYJl155U5fcc",
    "refreshToken": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6IjY4YTAxNDQzMmVmNjE1Mjc5YmMyMmQwOSIsInJvbGUiOiJVU0VSIiwiZW1haWwiOiJqb2huZG9lQGV4YW1wbGUuY29tIiwiaWF0IjoxNzU1MzIxNzMxLCJleHAiOjE3ODY4NTc3MzF9.e0R8QHJJLbSOXs9b5gMK5czfHRco9Le2BTwAos-wicA"
  }
}
```

---

### 3. **User Login**

**Method**: `POST`
**Endpoint**: `/auth/login`
**Description**: Logs in a user with email and password.

#### Input:

```json
{
  "email": "alphabytes.gpt@gmail.com",
  "password": "12345678"
}
```

#### Output:

```json
{
  "success": true,
  "message": "User login successfully",
  "data": {
    "user": {
      "_id": "686a63c11e3f704de3d8be69",
      "name": "Abdul Satter",
      "email": "abdulsatter.ism@gmail.com",
      "googleId": "",
      "role": "USER",
      "image": "/default/user.jpg",
      "subscription": false,
      "isDeleted": false,
      "verified": true,
      "createdAt": "2025-07-06T11:53:37.732Z",
      "updatedAt": "2025-07-06T11:55:13.239Z",
      "__v": 0
    },
    "accessToken": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6IjY4NmE2M2MxMWUzZjcwNGRlM2Q4YmU2OSIsInJvbGUiOiJVU0VSIiwiZW1haWwiOiJhYmR1bHNhdHRlci5pc21AZ21haWwuY29tIiwiaWF0IjoxNzUxODAzNTc4LCJleHAiOjE3NTQzOTU1Nzh9.kPQAVoMajOK_SCZ0EGecvnE74k3U-jdoibMMe9MuURo",
    "refreshToken": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6IjY4NmE2M2MxMWUzZjcwNGRlM2Q4YmU2OSIsInJvbGUiOiJVU0VSIiwiZW1haWwiOiJhYmR1bHNhdHRlci5pc21AZ21haWwuY29tIiwiaWF0IjoxNzUxODAzNTc4LCJleHAiOjE3ODMzMzk1Nzh9.uczp8yz-B_7bW43GfswX0gZ9JT5z1xrwxlert89WaY8"
  }
}
```

---

### 4. **Update Profile**

**Method**: `PATCH`
**Endpoint**: `/user/update-profile`
**Description**: Updates the user's profile information.

#### Input (FormData):

- `name` (String): Updated name of the user.
- `email` (String): Updated email address.
- `phone` (String): Updated phone number.
- `image` (File): Updated profile image.

#### Output:

```json
{
  "success": true,
  "message": "Profile updated successfully",
  "data": {
    "_id": "68a014432ef615279bc22d09",
    "name": "mr. user",
    "role": "USER",
    "email": "johndoe@example.com",
    "phone": "+1234567890",
    "image": "/images/300fit-1755322270386.jpeg",
    "verified": true,
    "createdAt": "2025-08-16T05:16:51.223Z",
    "updatedAt": "2025-08-16T05:31:10.697Z",
    "__v": 0
  }
}
```

---

### Notes:

- **Error Handling**: The API will return a `success: false` along with an appropriate error message if the request fails.
- **Authentication**: Use the `accessToken` returned from login or email verification for subsequent requests that require authentication.

---

This structure follows standard conventions, making the API documentation easy to read and understand.
