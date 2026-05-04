# 🎬 HubCinema – Auto Test Project

An automated testing project for the **HubCinema** movie ticketing website. The project uses the **Page Object Model (POM)** with test data managed in an Excel file, enabling structured execution and reporting.

Selenium tests run against these two frontend projects:
- https://github.com/Khanguyen2005/HubCinema-WebUser
- https://github.com/Khanguyen2005/HubCinema-WebAdmin

---

## 📌 Objectives

- Automate functional testing scenarios for the HubCinema web UI.
- Record actual results, pass/fail status, and screenshots directly into the Excel file.
- Ensure quality for key features such as registration, login, ticket booking, payment, cinema management, screening rooms, showtimes, food, news, and other admin functions.

---

## 🛠️ Technologies

| Technology | Version | Purpose |
|---|---|---|
| **C# / .NET** | .NET 8.0 | Primary language and runtime |
| **NUnit** | 3.14.0 | Unit and integration testing framework |
| **NUnit3TestAdapter** | 4.5.0 | Adapter to run NUnit in Visual Studio / dotnet test |
| **Selenium WebDriver** | 4.27.0 | Browser automation |
| **Selenium.Support** | 4.27.0 | Selenium utilities (waits, helpers) |
| **ChromeDriver** | 146.x | Drives Google Chrome |
| **ClosedXML** | 0.102.3 | Read test data and write results in Excel (.xlsx) |
| **Microsoft.NET.Test.Sdk** | 17.8.0 | Test discovery and execution SDK |
| **coverlet.collector** | 6.0.0 | Code coverage collection |
| **System.Drawing.Common** | 7.0.0 | Screenshot support |

---

## 📁 Project Structure

```
sqa-testing-report/
├── Data/
│   ├── DataTest.xlsx          # Excel file with test cases, data, and results
│   └── Screenshots/           # Screenshots saved after running tests
├── Models/
│   └── TestCaseStep.cs        # Model for a step in a test case
├── Pages/                     # Page Object Model – UI mappings
├── Tests/                     # Test classes by feature
├── Utilities/
│   ├── DriverFactory.cs       # ChromeDriver setup and configuration
│   ├── ExcelTestCaseHelper.cs # Read/write test cases to Excel
│   ├── PathHelper.cs          # File path management
│   └── ScreenshotHelper.cs    # Capture and save screenshots
└── sqa-testing-report.csproj
```

---

## 🧪 Test Scope

The project includes automated test cases for:

- **User authentication**: Register, Login, Update profile
- **Booking & Payment**: Choose movies, select seats, book tickets, pay
- **Cinema management**: Create/Update cinemas, rooms, seat maps
- **Showtime management**: Create and manage showtimes
- **Movie management**: Movie list (admin)
- **Food management**: Create and edit food items
- **News management**: Create news articles
- **Admin account management**: Create and update admin accounts
- **Admin login**: Verify admin authentication
- **Booked tickets**: View ticket history

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

> **Note:** The browser is visible by default when running tests. To run headless, uncomment `options.AddArgument("--headless")` in `Utilities/DriverFactory.cs`.

---

## 📊 Test Results

After execution, results are automatically recorded in `Data/DataTest.xlsx`, including:
- **Actual Result**: Observed outcome
- **Status**: Pass / Fail
- **Screenshots**: Associated screenshot file name
