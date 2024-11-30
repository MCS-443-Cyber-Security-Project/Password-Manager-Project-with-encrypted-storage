# Password-Manager-Project-with-encrypted-storage

This is a secure password manager project designed to store encrypted passwords and provide a user-friendly interface for managing them. Follow the instructions below to set up and run the project.

---

## **Requirements**
1. **XAMPP**: Ensure XAMPP is installed on your computer.
   - You can download it from [XAMPP Official Website](https://www.apachefriends.org/index.html).    
2. **Git** (optional): For cloning the repository directly instead of downloading a ZIP file.
3. **PHP-SUBLIME TEXT EDITOR**: Ensure Sublime Text editor is installed and run on your computer.
   -You can download it on: Sublime Official Website (https://www.sublimetext.com/) .
---

## **Installation Instructions**

### **Step 1: Download the ZIP File**
1. Go to the GitHub repository.
2. Click on the green **Code** button.
3. Select **Download ZIP**.

### **Step 2: Extract the ZIP File**
1. Locate the downloaded ZIP file.
2. Extract the contents to your preferred location.

### **Step 3: Move Project Files**
1. Navigate to the extracted folder.
2. Copy the entire folder.
3. Paste the folder into the `htdocs` directory of your XAMPP installation.
   - Default location for `htdocs`: `C:\xampp\htdocs\`.

### **Step 4: Start XAMPP**
1. Open the **XAMPP Control Panel**.
2. Start the following services:
   - **Apache**
   - **MySQL**

### **Step 5: Configure the Database**
1. Open your web browser and go to [phpMyAdmin](http://localhost/phpmyadmin).
2. Create a new database named (for example) `password_manager`.
3. Import the SQL file provided in the repository into the newly created database.
   - Use the **Import** tab in phpMyAdmin to upload the SQL file.
4. Create Database and Table using the following table:
CREATE DATABASE pass_manager;  //To create database name 'pass_manager'.
USE pass_manager;
CREATE TABLE users (                   // Create table 'users' from the database pass_mananger
    id INT AUTO_INCREMENT PRIMARY KEY,  
    username VARCHAR(50) NOT NULL UNIQUE,  
    email VARCHAR(100) NOT NULL UNIQUE,  
    password VARCHAR(255) NOT NULL  
);  
CREATE TABLE passwords (                 //Add another table with name 'passwords'.
    id INT AUTO_INCREMENT PRIMARY KEY,  
    user_id INT NOT NULL,  
    website VARCHAR(100) NOT NULL,  
    username VARCHAR(100) NOT NULL,  
    encrypted_password VARCHAR(255) NOT NULL,
    iv VARCHAR(255) NOT NULL,  
    FOREIGN KEY (user_id) REFERENCES users(id) ON DELETE CASCADE  
);  

////Then click the go buttom located at the bottom of the page...

### **Step 6: Access the Application**
1. Open your web browser and go to [http://localhost/your-folder-name](http://localhost/your-folder-name).
2. Login or register to start using the password manager.

---

## **Features**
- Secure storage for passwords with encryption.
- CRUD operations for managing passwords.
- Authentication with hashed passwords.
- User-friendly interface.

---

## **Troubleshooting**
1. **Apache or MySQL fails to start**:
   - Ensure no other applications are using port 80 or 3306.
   - Check for Skype or IIS running in the background.

2. **Cannot access the application**:
   - Double-check the project folder is in the `htdocs` directory.
   - Ensure the database name in the configuration file matches your phpMyAdmin setup.

---

## **Contributing**
Contributions are welcome! Please fork the repository and submit a pull request.

---

## **License**
This project is licensed under the [MIT License](LICENSE).

---

## **Support**
For issues or questions, feel free to open a GitHub issue or contact the maintainer.
