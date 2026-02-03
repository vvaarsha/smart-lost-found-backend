\# Backend – Day 2 Environment Setup \& Project Initialization



\## Project: Smart Lost \& Found System



\*\*Role:\*\* Member 2 – Backend \& Database Developer

\*\*Day:\*\* Day 2 (Environment Setup \& Initial Project Creation)

\*\*Goal:\*\* Prepare a complete backend development environment on Windows and create a runnable Spring Boot project



---



\## 1. Purpose of Day 2



Day 2 focuses on \*\*technical setup\*\*, not feature development. By the end of this day:



\* The backend project should \*\*run successfully\*\* on the local system

\* Database connection should be \*\*working\*\*

\* GitHub integration should be \*\*ready for daily commits\*\*

\* Backend work can proceed \*\*independently of frontend\*\*



---



\## 2. System Requirements (Windows)



The backend developer must ensure the following are installed on their Windows system:



\### 2.1 Required Software



\* Windows 10 / Windows 11

\* Java JDK 17 (Recommended)

\* IntelliJ IDEA / Eclipse / VS Code

\* MySQL Server

\* MySQL Workbench

\* Git

\* Postman



---



\## 3. Java Installation \& Verification



\### Steps:



1\. Install \*\*Java JDK 17\*\*

2\. Set environment variables:



&nbsp;  \* `JAVA\_HOME`

&nbsp;  \* Add Java `bin` path to `PATH`

3\. Verify installation:



```bash

java -version

```



Expected output should show Java 17.



---



\## 4. IDE Setup



\### Recommended IDE: IntelliJ IDEA



Steps:



\* Install IntelliJ IDEA Community Edition

\* Configure JDK in IDE settings

\* Enable Lombok plugin (important for reducing boilerplate code)



---



\## 5. Spring Boot Project Creation



\### Project Configuration



| Field        | Value              |

| ------------ | ------------------ |

| Project      | Maven              |

| Language     | Java               |

| Spring Boot  | Latest Stable      |

| Group        | com.lostfound      |

| Artifact     | lost-found-backend |

| Packaging    | Jar                |

| Java Version | 17                 |



\### Dependencies Selected



\* Spring Web

\* Spring Data JPA

\* MySQL Driver

\* Spring Security

\* Lombok

\* Validation



---



\## 6. Initial Project Structure Verification



After project creation, verify the following structure exists:



```

src/main/java/com/lostfound/

├── LostFoundApplication.java

src/main/resources/

├── application.properties

```



Run the application to confirm:



\* No errors

\* Server starts on port 8080



---



\## 7. Git \& GitHub Setup



\### Steps:



1\. Initialize Git repository



```bash

git init

```



2\. Create `.gitignore` file



Ignore:



\* `/target/`

\* `.idea/`

\* `.env`



3\. Create GitHub repository



\* Repository name: `smart-lost-found-backend`

\* Default branch: `main`



4\. Create backend working branch:



```bash

git checkout -b backend-branch

```



5\. Push initial commit



```bash

git add .

git commit -m "Day 2: Spring Boot project setup"

git push origin backend-branch

```



---



\## 8. Database Installation \& Setup



\### MySQL Configuration



1\. Install MySQL Server

2\. Create database:



```sql

CREATE DATABASE lost\_found\_db;

```



3\. Create MySQL user (optional):



```sql

CREATE USER 'lf\_user'@'localhost' IDENTIFIED BY 'password';

GRANT ALL PRIVILEGES ON lost\_found\_db.\* TO 'lf\_user'@'localhost';

```



---



\## 9. Spring Boot Database Configuration



Edit `application.properties`:



```properties

spring.datasource.url=jdbc:mysql://localhost:3306/lost\_found\_db

spring.datasource.username=lf\_user

spring.datasource.password=password



spring.jpa.hibernate.ddl-auto=update

spring.jpa.show-sql=true

spring.jpa.properties.hibernate.dialect=org.hibernate.dialect.MySQL8Dialect

```



Restart application and verify:



\* Application starts successfully

\* No database connection errors



---



\## 10. Postman Setup



Purpose:



\* Test backend APIs independently of frontend



Steps:



\* Install Postman

\* Create new collection: `Lost \& Found Backend`

\* Add placeholder requests for:



&nbsp; \* Register

&nbsp; \* Login

&nbsp; \* Lost Item API



---



\## 11. Folder \& Package Planning



Create empty packages to prepare future work:



```

com.lostfound.auth

com.lostfound.items

com.lostfound.ai

com.lostfound.claims

com.lostfound.notifications

com.lostfound.admin

com.lostfound.config

```



No code inside yet.



---



\## 12. Day 2 Deliverables



By the end of Day 2, the backend developer must have:



\* Running Spring Boot application

\* Connected MySQL database

\* GitHub repository with backend branch

\* Postman collection created

\* Base package structure ready



---



\## 13. Viva Reference Statement



> "On Day 2, I set up the complete backend development environment, created the Spring Boot project, configured MySQL database connectivity, initialized GitHub version control, and prepared the package structure for modular backend development."



---



\*\*Status:\*\* Day 2 Completed

\*\*Next Step:\*\* Day 3 – Database Schema Design \& Entity Creation



