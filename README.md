# ipt10-lab-db

Install xampp from the https://www.apachefriends.org/download.html

Run the installer and select Apache, MYSQL and Php

Open the xampp control panel and click start for both Apache and MySql

Enable extensions through the xampp control panel and click config
Click the php.ini
Find the lines inside the file
  extension=mysqli
  extension=pdo_mysql
Save the file and restart Apache

Database

go to phpmyadmin and go to sql tab and paste the following query

CREATE DATABASE IF NOT EXISTS ip10_lab
  CHARACTER SET utf8mb4
  COLLATE utf8mb4_0900_ai_ci;
USE ip10_lab;

CREATE TABLE students (
  id CHAR(36) NOT NULL,
  first_name VARCHAR(100) NOT NULL,
  middle_name VARCHAR(100) NULL,
  last_name VARCHAR(100) NOT NULL,
  birthday DATE NOT NULL,
  sex ENUM('Male', 'Female') NOT NULL,
  email VARCHAR(150) UNIQUE NOT NULL,
  student_number VARCHAR(50) UNIQUE NOT NULL,
  program VARCHAR(200) NOT NULL,
  enrolment_date DATE NOT NULL,
  created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
  updated_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP ON UPDATE CURRENT_TIMESTAMP,
  PRIMARY KEY (id)
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4;

INSERT INTO students
  (id, first_name, middle_name, last_name, birthday, sex,
   email, student_number, program, enrolment_date)
VALUES
  (UUID(), 'Maria', 'Cruz', 'Santos', '2005-06-15', 'Female',
   'maria@school.edu', 'STU001',
   'Bachelor of Science in Information Technology', '2024-09-01'),
  (UUID(), 'Juan', 'Delos', 'Dela Cruz', '2005-03-22', 'Male',
   'juan@school.edu', 'STU002',
   'Bachelor of Science in Information Technology', '2024-09-01'),
  (UUID(), 'Ana', 'Lopez', 'Reyes', '2005-11-08', 'Female',
   'ana@school.edu', 'STU003',
   'Bachelor of Science in Computer Science', '2024-09-02');


To run the application type

localhost/ipt10_lab/index.php
localhost/ipt10_lab_pdo/index.php
   
