# MotorPH Payroll System

Java desktop app for employee records, attendance, leave, and payroll.
Public project copy maintained by [Juan Carlos Miguel Basa](https://github.com/jayceebasa).

## Run on Windows

1. Install a **Java JDK 17 or newer**. Make sure `java` and `javac` work in PowerShell.
2. Click **Code → Download ZIP** on this page and extract it.
3. Open the extracted folder, then open **AOOP - MotorPH from OOP** and double-click **run.bat**.

The launcher builds and opens the app. The required Java libraries are included;
NetBeans, Docker, and Cloudflare are not needed just to build and open it.

**To sign in and use payroll, you also need the project's configured MySQL database.**
The public download does not include private database backups or passwords.
Ask the project maintainer for an authorized demo database and account. Installing
MySQL alone does not create the project's tables or test users.

On another PC, after restoring a compatible project database and applying the
[security migrations](security/migrations), create this file:

`%USERPROFILE%\.motorph\database.properties`

```properties
url=jdbc:mysql://127.0.0.1:3306/YOUR_DATABASE
user=YOUR_DATABASE_USER
password=YOUR_DATABASE_PASSWORD
```

Replace the placeholders with that PC's actual settings and run **run.bat** again.
Keep this file private. For the protected Milestone 2 environment and TLS setup,
see the [security guide](security/README.md). The prepared profile on the
maintainer's PC is Windows-user-specific and cannot be copied to another PC.

## Check the build without a database

From the repository folder, run:

```powershell
powershell -NoProfile -ExecutionPolicy Bypass -File scripts/build.ps1 -Test
```

These offline tests use test fixtures; they do not require or modify MySQL.

