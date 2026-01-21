# Check Master and NG Block program
![Status](https://img.shields.io/badge/Status-Ongoing-yellow)
![Platform](https://img.shields.io/badge/Platform-Windows%20Forms-8A2BE2)
![Tech](https://img.shields.io/badge/Tech-C%23%20%7C%20MSSQL-informational)

## 📌 Project Overview
&emsp; This project is designed to improve manufacturing accuracy by automating the Master Check process. The program monitors work values and checking patterns to ensure the machine is functioning correctly. If any error or incorrect pattern is detected, it triggers an electrical signal to stop the machine, requiring authorized access to unlock.

&emsp; Additionally, the system includes an "NG Block" feature that tracks each part’s history to ensure all previous processes were completed successfully. If a part skips a step or arrives with an "NG" status, the program alerts the operator and identifies which process error.

---

### 🔒 Note on Source Code
> **Disclaimer:**
> This project was developed professionally for a private client / company.
> Due to Non-Disclosure Agreements (NDA) and proprietary rights, the **source code cannot be made public**.
> This repository serves as a **showcase** of the application's functionality, UI design, and my technical contributions.

---

## 📸 Screenshots & Demo

## 1. Main menu page

![Mainmenu](images/Mainmenu.png)

"Description: Main menu for selecting data and programs. It also allows authorized users to adjust settings (login required)."

## 2. Check master page
![Master](images/Checkmaster.png)

"Description: A master check interface to verify if the workpiece is within specifications and follows the defined pattern."

## 3. NG Block page
| All pass | Detect skip | Detect NG skip |
|:---:|:---:|:---:|
| ![Pass](images/Pass.png) | ![Skip](images/Skipprocess.png) | ![NGSkip](images/NGSkip.png) |
| *All previous processes passed.* | *A previous process was skipped* | *A previous process was NG* |

*Description: A program to verify that all previous processes were passed and to check the result of the current process.*

---

## 🎯 Objectives

* **Check Machine Condition:** Verifies that the machine can inspecting all specific conditions and parameters defined for each workpiece.

* **Defect Outflow Prevention (Reduce NG):** Prevents defective parts into the next process by enforcing workpiece traceability and scheduling mandatory Master Workpiece checks.

* **Data Digitalization:** Transforms manual data recording and reporting into an automated digital system to ensure high accuracy and enable seamless historical data retrieval.

---

## 🏆 Benefits & Business Impact

### 1. Operational Efficiency
* **Paperless Operation:** Replaced manual paper recording with a fully digital system.
* **Reduced Cycle Time:** Decreased time spent on manual data entry, allowing operators to focus on production tasks.
* **Real-time Visibility:** Supervisors can monitor production status instantly via the dashboard without waiting for end-of-day reports.

### 2. Quality Control & Traceability
* **Human Error Reduction:** Minimized mistakes caused by manual data entry.
* **Traceability:** Instantly track product history to see when it was made, which machine was used, and who the operator was.
* **System Alert:** The system automatically alerts and stops the process if abnormalities occur (e.g., skipped steps or machine errors).

###  3. Data Integrity
* **Single Source:** Centralized all production data in the database, eliminating the need to manually collect data from individual machines.
* **Decision making:** Provides accurate data to help management make better decisions and improve production planning
---

## 🖧 System diagram
![Database Flow](images/Flowdiagram.png)

---

## ⚙️ Features

* **Process Traceability:** Validates workpiece process history. The system alerts the operator if a workpiece skipped or NG skipped any previous step.

* **IoT & Hardware Integration:** Establishes real-time data exchange with external IoT devices via Serial Port Communication for immediate measurement acquisition.

* **Check Master Alert:** Automatically notifies operators when a scheduled master check is required to verify machine accuracy and calibration status.

* **Automated Data Processing:** Streamlines the data workflow by reading raw files, filtering data, generating summary reports, and archiving results into the database.

* **Role-Based Access Control (RBAC):** Manages user permission (Admin, Engineer, Operator) to ensure data security and restrict unauthorized access.

---

## 🗄️ Database Architecture

### 📊 Schema Design Concept
* **Centralized Data:** Combine data from many production lines into one places.
* **Normalization:** Design tables using 3NF principles to reduce data redundancy.
* **Denormalized:** Store some duplicate data to make data retrieval faster and easier.

### 🧩 Diagram

![Master Database Flow](images/ER-MasterDiagram.png)

*Description: ER Diagram for the Master Check System. Designed for data collection.*

![NG Block Database Flow](images/ER-NGBlockDiagram.png)

*Description: ER Diagram for the NG Blocking system. Designed for data collection, workpiece traceability, and process validation.*


### 🚀 Performance & Scalability features
* **High Frequency Logging:** Designed to handle high-volume, concurrent data insertion from multiple machines simultaneously.
* **Smart Indexing:** Implemented `index` on frequently queried columns (e.g., Serial No., Date, Model) to optimize historical data retrieval speed.
* **Stored Procedures:** Migrated complex logic to the server side to minimize network traffic.

### 🔒 Security Implementation
* **Dedicated Database User:** Avoided using the `sa` (System Admin) account by creating a dedicated user account specifically for the application's connection.
* **Least Privilege Principle:** Restricted database permissions to essential CRUD Operations (Create, Read, Update, Delete) only, preventing unauthorized changes to the table structures or schema.
* **Stored Procedure Access:** Managed data access primarily via EXECUTE permissions on Stored Procedures to hide table structure and prevent SQL Injection risks.

---

## 🛠 Tech Stack
* **Language:** C#
* **Framework:** .NET Framework / Windows Forms
* **Database:** Microsoft SQL Server (MSSQL)
* **Tools:** Visual Studio, Git

---

## 💡 Technical Challenges & Solutions
* **Challenge:**
    * Managing high-frequency workpieces data from machine. 
    * Developing a single program adaptable to multiple production processes.
    * Connecting IoT devices to the software to read data and send electrical signals back to the machine.
* **Solution:** 
    * Designed the database to handle high-speed writing and used Stored Procedures to process data on the server (reducing the load on the C# app).

---

## 🚧 In Development & Roadmap
* [ ] **Phase 2:** Create Website to trace workpieces in each process
* [ ] **Phase 3:** Create Website to show if the master check was done on time.

---

## 📬 Contact Me
* **Name:** Pawarade Liangkobkij
* **Email:** l.pawarade@gmail.com
