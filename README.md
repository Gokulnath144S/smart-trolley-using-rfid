# 🛒 Smart Trolley Using RFID (LPC21xx)

## 📌 Overview

This project implements a **Smart Shopping Trolley** using RFID technology and an LPC21xx microcontroller. It allows automatic product detection, real-time billing, and item management (addition/removal) using RFID tags.

The system reduces manual billing effort and improves the shopping experience by displaying item count and total cost on an LCD.

---

## 🚀 Features

* 📡 RFID-based item scanning using UART
* ➕ Add items by scanning RFID tags
* ➖ Remove items using external interrupt
* 🧾 Real-time bill calculation
* 📟 LCD display for item count and total
* 💡 LED indication on billing
* ⚡ Interrupt-based control (EINT0 & EINT1)

---

## 🧰 Technologies Used

* Embedded C
* LPC21xx Microcontroller
* UART Communication
* Interrupt Handling
* LCD Interfacing

---

## 🔧 Hardware Components

* LPC2148 / LPC21xx Board
* RFID Reader Module
* RFID Tags
* 16x2 LCD Display
* Push Buttons (for interrupts)
* LEDs
* Power Supply

---

## ⚙️ Working Principle

1. Each product has a unique RFID tag ID.
2. RFID reader sends tag data via UART.
3. The system compares scanned ID with stored IDs:

   * `"0600679AE41F"` → Book 📘
   * `"060067DBFC46"` → Pen 🖊️
4. Item count is updated:

   * Scan → Add item
   * Press interrupt button → Remove item
5. Total price is calculated:

   * Book = ₹15
   * Pen = ₹10
6. LCD displays:

   * Item counts
   * Individual totals
   * Final total

---

## 🧮 Pricing Logic

```c id="b5z8r3"
#define PRICE1 15   // Book price
#define PRICE2 10   // Pen price

Total1 = bcount * PRICE1;
Total2 = pcount * PRICE2;
Total  = Total1 + Total2;
```

---

## 🔌 Interrupt Usage

* **EINT0** → Display total bill
* **EINT1** → Enable item removal mode

---

## 📁 Project Structure

```id="z3t8j2"
Smart-Trolley-RFID/
│── main.c
│── uart.h
│── lcdheader.h
│── intpt.h
│── README.md
```

---

## ▶️ How to Run

1. Connect RFID module to UART pins
2. Interface LCD with LPC21xx
3. Configure interrupts (EINT0, EINT1)
4. Compile code using Keil / Embedded IDE
5. Flash program to LPC2148
6. Power ON system
7. Scan RFID tags to add/remove items

---

## 🖥️ Sample Output

```
Book   2
Pen    1
Total  40
```

---

## 🔮 Future Improvements

* 📱 Mobile app integration
* ☁️ Cloud-based billing system
* 🧾 Automatic checkout system
* 🔐 Secure RFID authentication

---

## 👨‍💻 Author

GOKULNATH S
Electronics and communication engineering Graduate

---

## 📜 License

This project is open-source.

---

## 🙌 Acknowledgements

* Embedded Systems Community
* RFID Technology Developers

---
