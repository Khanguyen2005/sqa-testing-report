# 🎬 HubCinema – Automated Test Project

This repository contains automated UI testing for the HubCinema web applications. It is a test project for:
- https://github.com/Khanguyen2005/HubCinema-WebAdmin
- https://github.com/Khanguyen2005/HubCinema-WebUser

The suite focuses on Selenium-based end-to-end/functional tests. It does **not** provide unit tests for the API repository:
- https://github.com/Khanguyen2005/HubCinemaAPI

---

## 📌 Goals

- Automate functional test scenarios on the HubCinema web UI.
- Record actual results, pass/fail status, and screenshots directly into the Excel file.
- Cover key features such as registration, login, booking, payment, cinema management, screening rooms, showtimes, food items, news, and other admin functions.

---

## 🛠️ Tech Stack

| Technology | Version | Purpose |
|---|---|---|
| **C# / .NET** | .NET 8.0 | Primary language and runtime |
| **NUnit** | 3.14.0 | Test framework |
| **NUnit3TestAdapter** | 4.5.0 | NUnit adapter for Visual Studio / dotnet test |
| **Selenium WebDriver** | 4.27.0 | Browser automation |
| **Selenium.Support** | 4.27.0 | Selenium helpers (waits, utilities) |
| **ChromeDriver** | 146.x | Google Chrome automation |
| **ClosedXML** | 0.102.3 | Read test data and write results to Excel (.xlsx) |
| **Microsoft.NET.Test.Sdk** | 17.8.0 | Test discovery and execution SDK |
| **coverlet.collector** | 6.0.0 | Code coverage collection |
| **System.Drawing.Common** | 7.0.0 | Screenshot support |

---

## 📁 Project Structure

```
sqa-testing-report/
├── Data/
│   ├── DataTest.xlsx          # Excel file with test cases, data, and results
│   └── Screenshots/           # Screenshots saved after test runs
├── Models/
│   └── TestCaseStep.cs        # Model representing a test step
├── Pages/                     # Page Object Model mapping UI pages
├── Tests/                     # Test classes grouped by features
├── Utilities/
│   ├── DriverFactory.cs       # ChromeDriver initialization and configuration
│   ├── ExcelTestCaseHelper.cs # Read/write test cases from/to Excel
│   ├── PathHelper.cs          # Path utilities
│   └── ScreenshotHelper.cs    # Capture and save screenshots
└── sqa-testing-report.csproj
```

---

## 🧪 Test Scope

Automated test cases include:

- **User authentication**: Registration, Login, Profile update
- **Booking & Payment**: Select movie, choose seats, book tickets, pay
- **Cinema management**: Create/Update cinemas, rooms, seating maps
- **Showtime management**: Create and manage showtimes
- **Movie management**: Movie list (admin)
- **Food management**: Create and edit food items
- **News management**: Create news
- **Admin account management**: Create and update admin accounts
- **Admin login**: Admin-side authentication
- **Booked tickets**: View booking history

---

## 👥 Team Members

| Member | Test cases |
|---|---|
| Nguyễn Đàm Khá | 40 |
| Nguyễn Xuân Bắc | 40 |
| Lâm Tấn Thành | 40 |
| Trần Duy Khoa | 40 |

**Total: 160 automated test cases**

---

## 🚀 How to Run

### Requirements
- [.NET 8.0 SDK](https://dotnet.microsoft.com/download/dotnet/8.0)
- Google Chrome (compatible with the installed ChromeDriver)

### Run all tests

```bash
dotnet test
```

### Run a specific test

```bash
dotnet test --filter "FullyQualifiedName~<TestClassName>"
```

> **Note:** The browser runs in visible mode by default. To run headless, uncomment `options.AddArgument("--headless")` in `Utilities/DriverFactory.cs`.

---

## 📊 Test Results

After each run, results are written to `Data/DataTest.xlsx`, including:
- **Actual Result**
- **Status** (Pass / Fail)
- **Screenshots** (screenshot file names)
