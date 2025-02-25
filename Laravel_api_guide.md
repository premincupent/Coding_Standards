# Laravel API Guidelines

## 📋 **Table of Contents**
1. Introduction
2. Naming Conventions
3. HTTP Methods and Status Codes
4. Endpoint Structure
5. Request and Response Format
6. Pagination
7. Filtering and Sorting
8. Authentication and Authorization
9. Error Handling
10. Versioning
11. Security Best Practices
12. Logging and Monitoring
13. Testing APIs
14. Documentation Standards
15. Coding and Technical Guidelines
16. Using Query Arguments for Flexibility
17. Example API Endpoint Naming for Store Management
18. Best Practices

---

## 16. **Using Query Arguments for Flexibility**
Query arguments allow clients to customize API responses by filtering, sorting, and paginating results. Below are practical examples and use cases.

### **Filtering**
- Use query parameters to filter results by specific fields.

| **Query Parameter** | **Endpoint Example**                               | **Description**                                          |
|--------------------|-----------------------------------------|---------------------------------------------------------|
| `status`           | `/api/getAllStores?status=active`       | Retrieve active stores                                  |
| `city`             | `/api/getAllStores?city=Chennai`        | Retrieve stores located in Chennai                      |
| `category`         | `/api/getAllStores?category=grocery`    | Retrieve grocery stores                                 |

### **Sorting**
- Use `sort` and `order` parameters to sort results.

| **Parameter**      | **Endpoint Example**                                | **Description**                                                   |
|-------------------|---------------------------------------------------|-----------------------------------------------------------------|
| `sort=name`       | `/api/getAllStores?sort=name&order=asc`           | Sort stores by name in ascending order                           |
| `sort=created_at` | `/api/getAllStores?sort=created_at&order=desc`    | Sort stores by creation date in descending order                 |

### **Pagination**
- Use `page` and `limit` parameters for pagination.

| **Parameter**       | **Endpoint Example**                             | **Description**                                         |
|--------------------|-----------------------------------------------|-----------------------------------------------------|
| `page=1`           | `/api/getAllStores?page=1&limit=10`            | Retrieve the first page with 10 stores per page      |
| `page=2`           | `/api/getAllStores?page=2&limit=20`            | Retrieve the second page with 20 stores per page     |

### **Combining Arguments**
- Combine filtering, sorting, and pagination for flexible queries.

```plaintext
GET /api/getAllStores?status=active&city=Chennai&sort=name&order=asc&page=1&limit=10
```

**Description:** Retrieve active stores in Chennai, sorted by name in ascending order, with 10 stores per page on the first page.

---

## 17. **Example API Endpoint Naming for Store Management**
Follow a consistent naming pattern using verbs and PascalCase.

| **HTTP Method** | **Endpoint**                              | **Description**                                          |
|-----------------|-----------------------------------------|---------------------------------------------------------|
| `GET`           | `/api/getAllStores`                      | Retrieve all stores                                     |
| `GET`           | `/api/getStoreById/{id}`                 | Retrieve store details by ID                           |
| `POST`          | `/api/createStore`                       | Create a new store                                     |
| `PUT`           | `/api/updateStore/{id}`                  | Update store information                               |
| `PATCH`         | `/api/patchStore/{id}`                   | Partially update store information                     |
| `DELETE`        | `/api/deleteStore/{id}`                  | Delete a store                                         |

### **Path vs. Query Parameters**
- Use path parameters for resource identification.
- Use query parameters for filtering, sorting, and pagination.

### **Request and Response Examples**

**Request:**
```plaintext
GET /api/getStoreById/5
```

**Response:**
```json
{
    "success": true,
    "data": {
        "id": 5,
        "storeName": "SuperMart",
        "address": "123 Main Street",
        "phone": "1234567890",
        "email": "store@example.com",
        "status": "active"
    }
}
```

---

## 18. **Best Practices**
- Always validate query parameters to prevent abuse and security vulnerabilities.
- Provide clear error messages when invalid query parameters are used.
- Use default values for optional parameters to improve usability.
- Maintain comprehensive documentation for all available query arguments.

---

### ✅ **Conclusion**
Using query arguments for flexibility and following consistent endpoint naming ensures that APIs are intuitive, maintainable, and user-friendly. Always document available query arguments for each endpoint and adhere to best practices for security and performance.
