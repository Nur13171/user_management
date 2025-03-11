 ## **Laravel API Documentation**  

### **Table of Contents**  
- [Introduction](#introduction)  
- [Installation](#installation)  
- [Environment Setup](#environment-setup)  
- [Database Setup](#database-setup)  
- [Running the Application](#running-the-application)  
- [API Endpoints](#api-endpoints)  
- [Authentication](#authentication)  
- [Testing the API](#testing-the-api)  

---

## **Introduction**  
This is a **Laravel-based RESTful API** for user management. It provides endpoints for user authentication, CRUD operations, and role management.  

---

## **Installation**  

1. **Clone the repository**  
   ```sh
   git clone https://github.com/your-repo/your-project.git
   cd your-project
   ```

2. **Install dependencies**  
   ```sh
   composer install
   ```

3. **Create a `.env` file** (copy from example file)  
   ```sh
   cp .env.example .env
   ```

---

## **Environment Setup**  

1. **Generate application key**  
   ```sh
   php artisan key:generate
   ```

2. **Configure `.env` file**  
   Update the following fields in the `.env` file with your database and mail server credentials:  

   ```
   APP_NAME="Laravel API"
   APP_ENV=local
   APP_KEY=base64:xxxxxxxxxxxxxxxxxxxxxxxxxxx
   APP_DEBUG=true
   APP_URL=http://localhost:8000

   DB_CONNECTION=mysql
   DB_HOST=127.0.0.1
   DB_PORT=3306
   DB_DATABASE=your_database_name
   DB_USERNAME=your_database_user
   DB_PASSWORD=your_database_password
   ```

---

## **Database Setup**  

1. **Run database migrations**  
   ```sh
   php artisan migrate
   ```

2. **Seed the database**  
   ```sh
   php artisan db:seed
   ```

3. **(Optional) Reset & Seed**  
   ```sh
   php artisan migrate:fresh --seed
   ```

---

## **Running the Application**  

1. **Start the Laravel development server**  
   ```sh
   php artisan serve
   ```
   The application will now be accessible at:  
   **http://127.0.0.1:8000**

2. **Run Laravel queue (if required)**  
   ```sh
   php artisan queue:work
   ```

---

## **API Endpoints**  

### **Authentication**  
| Method | Endpoint            | Description             |
|--------|---------------------|-------------------------|
| POST   | `/api/register`     | Register a new user    |
| POST   | `/api/login`        | Login and get a token  |
| POST   | `/api/logout`       | Logout the user        |

### **User Management**  
| Method | Endpoint            | Description                  |
|--------|---------------------|------------------------------|
| GET    | `/api/users`        | Get all users               |
| GET    | `/api/users/{id}`   | Get a specific user         |
| POST   | `/api/users`        | Create a new user           |
| PUT    | `/api/users/{id}`   | Update an existing user     |
| DELETE | `/api/users/{id}`   | Delete a user               |

---

## **Authentication**  
This API uses Sanctum authentication. After logging in, you will receive a token that should be passed in the request headers:

```
Authorization: Bearer {TOKEN}
```

Example request using **cURL**:  

```sh
curl -X GET "http://127.0.0.1:8000/api/users" \
-H "Authorization: Bearer YOUR_ACCESS_TOKEN"
```

---

## **Testing the API**  

1. **Using Postman**  
   - Import the API collection and test endpoints.  
   - Include the **Authorization Token** in the headers.  

2. **Using Laravel Artisan**  
   ```sh
   php artisan test
   ```

3. **Using cURL**  
   Example request to fetch users:  
   ```sh
   curl -X GET "http://127.0.0.1:8000/api/users"
   ```

---

## **Troubleshooting**  

- **If `.env` changes don’t apply**, run:  
  ```sh
  php artisan config:clear
  php artisan cache:clear
  ```
- **If migration issues occur**, try:  
  ```sh
  php artisan migrate:fresh --seed
  ```
- **If Composer dependencies fail**, try:  
  ```sh
  composer install --no-cache
  ```
'




