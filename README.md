# CineWave Ticket Booking Management System (Pega Infinity v8.x / v25.x)

![Pega](https://img.shields.io/badge/Pega_Platform-Infinity_v8.x%2Fv25.x-blue?style=for-the-badge&logo=pega)
![Status](https://img.shields.io/badge/Status-Completed-success?style=for-the-badge)
![Category](https://img.shields.io/badge/Domain-Information_Technology-orange?style=for-the-badge)

An automated low-code **Movie Ticket Booking Management System** built on **Pega Platform™** for **CineWave Entertainment**. This solution transforms manual email/offline booking workflows into a streamlined digital case management process featuring dynamic pricing calculations, seat availability verification, SLA management, automated email confirmations, and role-based work routing.

---

## 📌 Business Overview & Objectives

**CineWave Entertainment** operates across multiple cinema locations and theatres. Previously, ticket bookings and tracking were handled via emails and offline spreadsheets, leading to delays, high error rates, and zero real-time visibility.

### Key Objectives Achieved:
1. **End-to-End Case Lifecycle**: Designed an enterprise-grade Pega Case Type (`Ticket Booking`).
2. **Dynamic UI/UX**: Implemented interactive screens for show selection, dynamic seat picking, and order review.
3. **Automated Business Logic**: Automated seat dynamic pricing calculations, taxes, and total cost evaluations.
4. **SLA & Routing**: Enforced Service Level Agreements (SLAs) for quick processing and routed high-priority requests (e.g., IMAX/VIP shows) to specialized staff queues.
5. **Real-time Notifications**: Automated email delivery of booking confirmations and e-tickets upon completion.

---

## 🏗️ Pega Architecture & Design Details

### 1. Case Lifecycle Design (`Ticket Booking` Case Type)
* **Create Stage**: Captures customer details, location, theatre, movie, show time, and seat count.
* **Review & Validate Stage**: Automated availability check; user confirmation step[cite: 1].
* **Fulfillment Stage**: Payment processing/cash desk verification and automated email trigger[cite: 1].

---

### 2. Data Model & Data Types

| Data Type | Field Name | Type | Description |
| :--- | :--- | :--- | :--- |
| **`CustomerDetails`** | `FullName`, `Email`, `Phone` | Text, Email, Phone | Customer personal contact information. |
| **`ShowDetails`** | `TheatreName`, `MovieName`, `ShowType`, `ShowTime` | Picklist / Text | Metadata for theatres (Standard, VIP, IMAX) and movies. |
| **`BookingDetails`** | `SeatCategory`, `Quantity`, `UnitPrice`, `TotalPrice` | Text, Integer, Currency | Seat details & dynamic pricing values. |

---

### 3. User Stories Implemented

* **`US-001` Submit Movie Ticket Request**: User form with data validation for customer & show inputs[cite: 1].
* **`US-002` Check Show Availability**: Automated rule evaluating available inventory against requested tickets[cite: 1].
* **`US-003` Calculate Booking Cost**: Data Transform/Declare Expression calculating `TotalPrice = (Quantity * UnitPrice) + Taxes`[cite: 1].
* **`US-004` Confirm Booking Request**: Review screen capturing explicit customer approval prior to locking booking[cite: 1].
* **`US-005` Maintain Movie & Show Data**: Data Records management in Pega App Studio[cite: 1].
* **`US-006` Review Booking Details**: Summarized review harness before final submission[cite: 1].
* **`US-007` Process Ticket Booking**: Assignment step for Box Office staff / automated payment approval[cite: 1].
* **`US-008` Notify Booking Confirmation**: Correspondence rule triggering automated HTML ticket confirmation email[cite: 1].
* **`US-009` Define Booking SLA**: Goal (30 mins), Deadline (2 hrs) SLA configured on approval assignments[cite: 1].
* **`US-010` Route Booking Request by Show Type**: Worklist/Workbasket routing rule based on `ShowType` (e.g., IMAX → VIP Workbasket, Standard → General Queue)[cite: 1].

---

## 📂 Repository Structure

├── documentation/
│   ├── Architecture_Diagram.png
│   ├── Case_Lifecycle.png
│   ├── Data_Model_ERD.png
│   └── CineWave_Project_Submission_Report.pdf
├── screenshots/
│   ├── US001_SubmitRequest.png
│   ├── US003_CostCalculation.png
│   ├── US008_EmailNotification.png
│   └── US010_RoutingAndSLA.png
└── README.md
---

## 📹 Video Demo Link
[Watch Demo Video on YouTube]
