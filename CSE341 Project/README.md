# 🎬 Movie Ticket Booking System (8086 Assembly)

A comprehensive Console-Based Movie Ticket Booking System developed in 8086 Assembly Language. This project simulates a real-world ticketing system with features including seat visualization, booking management, pricing calculation, and cancellation logic, all running within the 16-bit DOS environment.

## 🚀 Features

- **Interactive Menu System**: Easy-to-navigate main menu loop.
- **Visual Seat Map**: Displays real-time seating availability (Matrix format) where `0` represents available and `X` represents booked.
- **Multiple Movies & Halls**: Supports 6 different movies across 3 different cinema halls with specific showtimes.
- **Booking Engine**:
  - Input validation for seat numbers.
  - Conflict detection (prevents double booking).
  - Price calculation based on the specific movie selected.
- **Booking History**: Stores customer names and booking details using custom data structures.
- **Cancellation System**: Allows users to cancel tickets by name, automatically freeing up the seat in memory and shifting array data to maintain integrity.

## 🛠️ Technical Implementation

This project demonstrates advanced low-level programming concepts:

- **Memory Management**: Uses the Small Memory Model. Direct manipulation of memory segments to store seat maps and user data.
- **Parallel Arrays (Struct Simulation)**: Since Assembly lacks high-level structs, this project uses parallel arrays (`BOOKING_SEATS`, `BOOKING_NAMES`, etc.) sharing a common index to link data.
- **Bitwise Operations**: Efficient multiplication using `SHL` (Shift Left) for calculating memory offsets.
- **Custom I/O Procedures**: Implemented custom procedures for:
  - `READ_NUMBER`: Processing multi-digit integer input from characters.
  - `PRINT_NUMBER`: Converting register values to ASCII for display.
  - `REMOVE_BOOKING`: Complex algorithm to shift array elements upon cancellation to fill memory gaps.

## 💻 Prerequisites

To run this project, you need an 8086 emulator.

- **Recommended**: Emu8086 (Simplest setup, includes assembler and emulator).
- **Alternative**: DOSBox with TASM or MASM.

## 📥 How to Run

### Using Emu8086:

1. Clone this repository or download the source code.
2. Open `main.asm` (or whatever you named the file) in Emu8086.
3. Click the Emulate button.
4. A generic terminal window will appear. Click Run to start the application.

### Using MASM/TASM (DOSBox):

1. Mount your directory in DOSBox.
2. Compile the object file:
   ```bash
   masm main.asm;
   ```
3. Link the object file:
   ```bash
   link main.obj;
   ```
4. Run the executable:
   ```bash
   main.exe
   ```

## 📸 Usage Example

### 1. Main Menu
```
===== MOVIE TICKET BOOKING SYSTEM =====
1. Select Movie & Book Seat
2. View Available Seats
3. View Booking History
4. Cancel Booking by Name
5. Exit
Choose option: 
```

### 2. Seating Map (Hall 1)
```
=== HALL 1 - Time: 10:00 AM ===
Seating Layout (0=Available, X=Booked):
Row 5: 0 0 0 0 0 0 
Row 4: 0 0 X X 0 0 
Row 3: 0 0 0 0 0 0 
Row 2: 0 0 0 0 0 0 
Row 1: 0 0 0 0 0 0 
```

## 🤝 Contribution

Feel free to fork this repository and submit pull requests. Suggestions for optimizing the array shifting algorithm or adding file handling for persistent storage are welcome!

## 📜 License

This project is open-source and available for educational purposes.

## 👨‍💻 Author

**Raiyan Rahman**

**University**: BRAC University
**Course**: CSE341: Microprocessors