# HubCinema - Automated Testing Report

<p align="center">
  <img src="https://img.shields.io/badge/C%23-239120?logo=csharp&logoColor=white&style=flat" />
  <img src="https://img.shields.io/badge/.NET%208-512BD4?logo=dotnet&logoColor=white&style=flat" />
  <img src="https://img.shields.io/badge/Selenium-43B02A?logo=selenium&logoColor=white&style=flat" />
  <img src="https://img.shields.io/badge/NUnit-25A162?logo=nunit&logoColor=white&style=flat" />
</p>

## Introduction

HubCinema - Automated Testing Report is a Selenium-based functional UI testing project for both **HubCinema-WebUser** (customer frontend) and **HubCinema-WebAdmin** (admin frontend). It validates end-to-end flows such as authentication, booking tickets, payment, and cinema management, and records results into Excel reports.

Other components in the HubCinema ecosystem:

- **HubCinemaAPI (Backend for User & Admin):** https://github.com/Khanguyen2005/HubCinemaAPI
- **HubCinema-WebUser (Customer Frontend):** https://github.com/Khanguyen2005/HubCinema-WebUser
- **HubCinema-WebAdmin (Admin Frontend):** https://github.com/Khanguyen2005/HubCinema-WebAdmin

## Tech Stack

| Category | Technology | Version | Notes |
| --- | --- | --- | --- |
| Language & Runtime | C# / .NET | .NET 8.0 | Test project runtime |
| Test Framework | NUnit | 3.14.0 | Test execution and assertions |
| Browser Automation | Selenium WebDriver | 4.27.0 | UI automation APIs |
| Browser Driver | ChromeDriver | 146.x | Drives Google Chrome |
| Data & Reporting | ClosedXML | 0.102.3 | Read/write Excel test data and results |

## Architecture & Folder Structure

The project applies **Page Object Model (POM)** for maintainable UI selectors and flows, combined with **Data-Driven Testing** where test inputs and outputs are stored in Excel. Each test reads data from `Data/DataTest.xlsx`, executes UI steps, then writes **Pass/Fail** status and screenshots back to the same workbook.

```
sqa-testing-report/
├── Data/
│   ├── DataTest.xlsx          # Excel test data and results
│   └── Screenshots/           # UI screenshots captured during test runs
├── Models/                    # Test case models
├── Pages/                     # Page Objects (POM)
├── Tests/                     # Test cases grouped by features
├── Utilities/                 # Driver, Excel, path, and screenshot helpers
└── sqa-testing-report.csproj
```

## Getting Started

### 1) Clone and restore

```bash
git clone https://github.com/Khanguyen2005/sqa-testing-report.git
cd sqa-testing-report

dotnet restore
```

### 2) Prepare ChromeDriver

- Install **Google Chrome**.
- Ensure the **ChromeDriver** version matches your installed Chrome version.
- The project references `Selenium.WebDriver.ChromeDriver`; update the package if you need a different driver build.

### 3) Run tests

```bash
dotnet test
```

### 4) View reports

- Excel report: `Data/DataTest.xlsx`
- Screenshots: `Data/Screenshots/`

## Key Features/Test Scope

- Automated functional UI scenarios for both customer and admin frontends.
- Records **Pass/Fail** status and embeds screenshot evidence in Excel.
- **160 automated test cases** (40 test cases per member).
- Coverage includes:
  - **User flows:** Auth, browsing movies, selecting showtimes, seat layout selection, book tickets, payment.
  - **Admin flows:** Auth, cinema management (cinema clusters/rooms/seat layout), showtimes scheduling, movie management, food/combos management, news management, user/admin account management.

## Contributors

- Khá
- Bắc
- Khoa
- Thành
