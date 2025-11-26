# Hotel Management System 🏨
![Java](https://img.shields.io/badge/Java-ED8B00?style=for-the-badge&logo=openjdk&logoColor=white)
![Status](https://img.shields.io/badge/Status-Active-success?style=for-the-badge)
![License](https://img.shields.io/badge/License-MIT-blue?style=for-the-badge)

**Features:** Room Booking · Food Ordering · Billing System · Data Persistence · Customer Management
A comprehensive Java-based console application for managing hotel operations including room reservations, food ordering, billing, and customer management.

## 📋 Table of Contents

- [Overview](#overview)
- [Features](#features)
- [System Architecture](#system-architecture)
- [Room Types](#room-types)
- [Getting Started](#getting-started)
- [Usage Guide](#usage-guide)
- [Technical Details](#technical-details)
- [Future Enhancements](#future-enhancements)

## 🎯 Overview

This Hotel Management System is designed to streamline hotel operations by providing an integrated solution for managing room bookings, customer information, food orders, and billing. The system uses object serialization for data persistence, ensuring that all booking and customer data is preserved between sessions.

## ✨ Features

- **Room Management**
  - Multiple room categories (Luxury/Deluxe, Single/Double)
  - Real-time room availability checking
  - Room booking with customer details
  - Support for single and double occupancy

- **Food Service**
  - In-room food ordering system
  - Menu with multiple items and pricing
  - Automatic bill calculation including food charges

- **Billing System**
  - Comprehensive billing with room charges
  - Itemized food charges
  - Automatic total calculation
  - Checkout process with bill generation

- **Data Persistence**
  - Serialization-based data storage
  - Automatic backup on exit
  - Data restoration on startup

- **User-Friendly Interface**
  - Console-based menu system
  - Input validation and error handling
  - Clear navigation options

## 🏗️ System Architecture

### Core Classes

#### **Food**
Handles food ordering and pricing
- Attributes: `itemno`, `quantity`, `price`
- Automatically calculates price based on item and quantity
- Menu items: Sandwich (₹50), Pasta (₹60), Noodles (₹70), Coke (₹30)

#### **Singleroom**
Manages single occupancy rooms
- Attributes: `name`, `contact`, `gender`, `food` (ArrayList)
- Base class for room management
- Tracks customer details and food orders

#### **Doubleroom**
Extends Singleroom for double occupancy
- Additional attributes: `name2`, `contact2`, `gender2`
- Manages two guests per room
- Inherits food ordering capabilities

#### **NotAvailable**
Custom exception for handling unavailable rooms
- Thrown when attempting to book an already occupied room
- Provides clear error messaging

#### **holder**
Data container for all hotel rooms
- Luxury Double Rooms: 10 rooms (Room #1-10)
- Deluxe Double Rooms: 20 rooms (Room #11-30)
- Luxury Single Rooms: 10 rooms (Room #31-40)
- Deluxe Single Rooms: 20 rooms (Room #41-60)
- Total capacity: 60 rooms

#### **Hotel**
Main business logic class
- Static methods for all hotel operations
- Methods:
  - `CustDetails()`: Captures customer information
  - `bookroom()`: Handles room booking process
  - `features()`: Displays room amenities
  - `availability()`: Shows available rooms
  - `bill()`: Generates customer bill
  - `deallocate()`: Processes checkout
  - `order()`: Manages food ordering

#### **write**
Implements Runnable for data persistence
- Saves hotel data to file using serialization
- Runs as separate thread on program exit
- Creates backup file for data recovery

## 🛏️ Room Types

| Room Type | Beds | AC | Breakfast | Charge/Day | Room Numbers |
|-----------|------|----|-----------|-----------:|--------------|
| Luxury Double | 1 Double | ✓ | ✓ | ₹4,000 | 1-10 |
| Deluxe Double | 1 Double | ✗ | ✓ | ₹3,000 | 11-30 |
| Luxury Single | 1 Single | ✓ | ✓ | ₹2,200 | 31-40 |
| Deluxe Single | 1 Single | ✗ | ✓ | ₹1,200 | 41-60 |

## 🚀 Getting Started

### Prerequisites

- Java Development Kit (JDK) 8 or higher
- Command-line interface (Terminal/Command Prompt)

### Installation

1. Clone the repository:
```bash
git clone https://github.com/yourusername/hotel-management-system](https://github.com/AbhiramMandala/-Hotel-Management-System.git
cd hotel-management-system
```

2. Compile the Java file:
```bash
javac Main.java
```

3. Run the application:
```bash
java Main
```

## 📖 Usage Guide

### Main Menu Options

1. **Display Room Details**
   - View amenities and pricing for each room type
   - Select room category to see specific features

2. **Display Room Availability**
   - Check number of available rooms by category
   - Real-time availability status

3. **Book a Room**
   - Select room type
   - Choose from available room numbers
   - Enter customer details (name, contact, gender)
   - For double rooms, enter details for both guests

4. **Order Food**
   - Enter room number
   - Select items from menu
   - Specify quantities
   - Order multiple items in one session

5. **Checkout**
   - Enter room number
   - View complete bill (room + food charges)
   - Confirm checkout
   - Room becomes available for new bookings

6. **Exit**
   - Automatically saves all data
   - Creates backup file for next session

### Sample Workflow

```
1. Book a Luxury Double Room (#5)
2. Enter customer details for two guests
3. Order food (Pasta x2, Coke x2)
4. Checkout and view bill:
   - Room Charge: ₹4,000
   - Food Charges: ₹180 (Pasta: ₹120, Coke: ₹60)
   - Total: ₹4,180
```

## 🔧 Technical Details

### Technologies Used
- **Language**: Java
- **I/O**: Scanner for user input
- **Persistence**: Object Serialization (ObjectInputStream/ObjectOutputStream)
- **Concurrency**: Threading for data backup
- **Exception Handling**: Custom and built-in exceptions

### Data Persistence
- All room and booking data is saved to a `backup` file
- Automatic restoration on application startup
- Thread-based asynchronous saving on exit

### Error Handling
- Invalid room number detection
- Room availability validation
- Input validation for menu choices
- Null pointer exception handling for unbooked rooms
- Custom NotAvailable exception for occupied rooms

## 🔮 Future Enhancements

- [ ] GUI interface using JavaFX or Swing
- [ ] Database integration (MySQL/PostgreSQL)
- [ ] Multi-day booking support
- [ ] Payment gateway integration
- [ ] Customer history and loyalty program
- [ ] Staff management module
- [ ] Room service tracking
- [ ] Reporting and analytics
- [ ] Email confirmation system
- [ ] Online booking portal

## 📝 Notes

- The system uses 0-based indexing internally but displays 1-based room numbers to users
- All data is stored in a single serialized file named `backup`
- Room numbers are mapped to array indices automatically
- The application requires proper program termination to save data

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## 📄 License

This project is open source and available under the [MIT License](LICENSE).

## 👨‍💻 Author

ABHIRAM - [GitHub Profile](https://github.com/AbhiramMandala)

## 📧 Contact

For questions or feedback, please reach out via [abhirammandala02@gamil.com](mailto:abhirammandala02@gamil.com)

---

**Note**: This is a console-based application designed for educational purposes and demonstrates core Java concepts including OOP, exception handling, file I/O, and serialization.
