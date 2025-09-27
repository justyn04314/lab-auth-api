Project Overview 

This is a simple authentication API built with Express.js, MySQL, and JWT. It allows users to sign up, 
log in, log out, and view their profile using a token system with configurable expiration and the passwords are safely stored, 
and tokens can be revoked when a user logs out. 

Set-up and How to run:
1. Install the necessary software like ( Node.js Gitbash postman, vs code, Xampp) 
2. Open Xampp and start APache and mySQL 
3. Go to phpMyadmin (http://localhost/phpmyadmin). 
4. Create a user account and a data called “lab_auth”
5. Paste these code in the sql to create a two tables
6. Open the VS code and do the these structure 
 - CREATE TABLE IF NOT EXISTS users ( id INT AUTO_INCREMENT PRIMARY KEY, email VARCHAR(100) NOT NULL UNIQUE,
   password_hash VARCHAR(255) NOT NULL, full_name VARCHAR(120), role VARCHAR(30) DEFAULT 'student',
   created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP ) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4;
   
- CREATE TABLE IF NOT EXISTS revoked_tokens ( id INT AUTO_INCREMENT PRIMARY KEY, jti VARCHAR(64) NOT NULL UNIQUE,
 expires_at DATETIME NOT NULL, revoked_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP ) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4;

7. In your project folder, update .env file with your database credentials
8. Run the project in terminal Npm run dev
9. Test in browser http://localhost:3000/api/health
10. If it shows “ok” or “connected” the setip is successful 


API ENDPOINTS 
- POST {{baseUrl}}/auth/signup - register a new user 
- POST {{baseUrl}}/auth/login - Login and get token
- GET {{baseUrl}}/profile - Get user profile (requires token) 
- POST {{baseUrl}}/auth/logout - Logout and revoke current token this is my previous read me and now update it 









