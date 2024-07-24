# README for Parking Management System

This project implements a parking management system for a parking lot. The system handles vehicle entries and exits, calculates parking fees, manages parking space allocation, and records all transactions in a CSV file.

Features
1. **Parking Record Management:**
   - Initialize the parking records CSV file with appropriate headers.
   - Read and manage parking records from the CSV file, including error handling.

2. **Vehicle Entry and Exit:**
   - Validate vehicle license plates based on the UK format.
   - Assign available parking spaces to vehicles and generate unique ticket numbers.
   - Calculate parking fees based on the duration of the stay.
   - Record vehicle exits and update the parking space availability.

3. **Parking Lot Management:**
   - Track available and occupied parking spaces.
   - Display information about available spaces.
   - Query and display detailed parking records based on ticket numbers.

## Project Structure

- **Libraries Used:**
  - `os`, `csv`, `datetime`, `random`, `string`, `re`: Standard Python libraries for file handling, date-time operations, random string generation, and regular expressions.

- **Files:**
  - `parking_records.csv`: The main data file storing parking records with headers including `vehicle_number`, `ticket_number`, `entry_time`, `exit_time`, `space_number`, `status`, `duration`, `fee`.

## Core Functions and Classes

1. **create_parking_records_file(file_path)**:
   - Initializes the CSV file if it does not exist.

2. **read_parking_records(file_path)**:
   - Reads parking records from the CSV file with error handling for missing files and I/O errors.

3. **is_valid_license_plate(plate)**:
   - Checks if the entered license plate matches the UK format.

4. **class ParkingLot**:
   - **__init__()**: Initializes the parking lot with total spaces and records.
   - **save_parking_records(file_path)**: Saves the current and exited vehicle records to the CSV file.
   - **find_next_available_space()**: Finds the next available parking space.
   - **enter_vehicle(registration_number)**: Handles vehicle entry, assigns space, and generates ticket.
   - **calculate_parking_fee(entry_time, exit_time, rate_per_hour=2)**: Calculates parking fees.
   - **exit_vehicle(registration_number)**: Manages vehicle exit, updates records, and calculates fees.
   - **display_available_spaces()**: Displays the number of available parking spaces.
   - **query_parking_record(ticket_number)**: Queries and returns parking record details based on ticket numbers.

## Usage

1. Initialize the parking lot and records.
2. Use `enter_vehicle` to add a vehicle to the parking lot.
3. Use `exit_vehicle` to process a vehicle's departure.
4. Use `display_available_spaces` to check available spaces.
5. Use `query_parking_record` to retrieve detailed parking information based on a ticket number.
