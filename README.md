# VehicleBookingApp_onNext
The project is built on Nex.js.15 and MySQL 


### Database Queries
```sql
=========================================================
Create database VehicleBooking;
use VehicleBooking;

CREATE TABLE VehicleTypes (
    id INT PRIMARY KEY AUTO_INCREMENT,
    type VARCHAR(50) NOT NULL
);


CREATE TABLE Vehicles (
    id INT PRIMARY KEY AUTO_INCREMENT,
    typeId INT NOT NULL,
    name VARCHAR(100) NOT NULL,
    FOREIGN KEY (typeId) REFERENCES VehicleTypes(id)
);
ALTER TABLE Vehicles 
ADD registrationNumber VARCHAR(50);


CREATE TABLE Bookings (
    id INT PRIMARY KEY AUTO_INCREMENT,
    vehicleId INT NOT NULL,
    name VARCHAR(100) NOT NULL,
    startDate DATE NOT NULL,
    endDate DATE NOT NULL,
    FOREIGN KEY (vehicleId) REFERENCES Vehicles(id)
);

ALTER TABLE Bookings 
ADD firstName VARCHAR(50) NOT NULL, 
ADD lastName VARCHAR(50) NOT NULL;
==============================================================
INSERT INTO VehicleTypes (type) VALUES ('Hatchback'), ('SUV'), ('Sedan'), ('Cruiser'), ('Sports');
INSERT INTO Vehicles (typeId, name) VALUES 
(1, 'Hyundai i10'), (2, 'Toyota Fortuner'), 
(3, 'Honda Accord'), (4, 'Harley Davidson'), 
(5, 'Kawasaki Ninja');

====================================================================
Select * from VehicleTypes;
Select * from Vehicles;
Select * from Bookings;
============================================



