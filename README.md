# Student Transaction Processing System 

## Description / Overview

The **Student Transaction Processing System (STPS)** is a web-based CRUD application developed using the **Laravel Framework**.  

It allows users to manage **student records** and their corresponding **financial transactions** efficiently — including adding, editing, deleting, and viewing records.  

The system demonstrates Laravel’s **MVC architecture**, **Blade templating**, and **Object Relational Mapping (ORM) relationships** between **students** and **transactions**.

---

## Objectives

- To develop a functional **transaction processing system** using Laravel.  
- To apply the **MVC architecture** for clean separation between logic, data, and presentation.  
- To demonstrate **one-to-many Eloquent relationships** (`hasMany`, `belongsTo`) between students and transactions.  
- To implement **CRUD functionality** for both tables.  
- To apply Blade templates for organized and reusable front-end layouts.  

---

## Features / Functionality

###  Student Management
- Add new students with fields such as:
  - Student Number
  - Name
  - Section
  - Email
- View all students in a table with their current balance.
- Edit or delete existing student information.
- View detailed student profiles including all related transactions.







### Transaction Management
- Record, edit, or delete student transactions.
- Each transaction includes:
  - Transaction Type (e.g., Payment, Fee, Refund)
  - Amount
  - Remarks
  - Processed Date
- Automatically calculates total student balance.

### Relationships
Implements **One-to-Many Relationship** using Eloquent ORM:

```php
// In Student model
public function transactions() {
    return $this->hasMany(Transaction::class);
}

// In Transaction model
public function student() {
    return $this->belongsTo(Student::class);
}
```

## Installation Instruction

### 1. Navigate to your Laravel project folder
cd student-transaction-system

### 2. Install dependencies
composer install

### 3. Copy the example environment file
cp .env.example .env

### 4. Configure database credentials in .env
DB_DATABASE=student_transactions
DB_USERNAME=root
DB_PASSWORD=

### 5. Generate application key
php artisan key:generate

### 6. Run migrations and seeders
php artisan migrate --seed

### 7. Start the Laravel development server
php artisan serve

## Usage

1. Click **Students** in the navigation bar to manage student records.  
2. Click **Add Student** to register a new student.  
3. Click **Transactions** to view or create new transactions.  
4. Use **Edit** or **Delete** buttons to modify records.  
5. Click a student’s name to view their transaction history and balance.

## Screenshots

### 1. Student List
![Student List](students-list.png)

### 2. Transaction List
![Transaction List](transactions-list.png)

### 3. Add Student Form
![Add Student](add-student.png)

### 4. Add Transaction Form
![Add Transaction](add-transaction.png)

### 5. Student Details
![Student Details](student-details.png)

##  Code Snippets

### Relationship Example
```php
// Student.php
public function transactions() {
    return $this->hasMany(Transaction::class);
}

// Transaction.php
public function student() {
    return $this->belongsTo(Student::class);
}
```

## Contributor

- **[Adrian Jovel E. Viernes]** — Developer  
  BS Information Technology 4D

##  License

This project is created for **educational purposes only** as part of the Midterm Examination in Web Systems and Technologies.  


