# Online Shopping Portal — JSP + JavaBeans E-Commerce App 🛒

A **full-stack e-commerce web application** built with **JSP, JavaBeans, Servlets, JDBC, and Oracle XE**, deployed on **Oracle WebLogic Server**. Features 7 product categories, session-based cart, cookie-based login, and automatic schema creation on startup.

## 📸 Preview
<img width="960" height="1020" alt="Screenshot 2026-10-01 115017" src="https://github.com/user-attachments/assets/522a05ab-a930-4908-997a-a357790f1a43" />


## 📖 Overview

**Online Shopping Portal** is a Java web application demonstrating the **JSP Model 1 architecture** — JSPs handle both presentation and control flow, delegating business logic to JavaBeans and persistence to JDBC. A startup servlet reads configuration from `web.xml` and initializes the database schema automatically.

**Built to practice:**
- **JSP scriptlets, directives, and standard actions** (`<jsp:useBean>`, `<jsp:setProperty>`, `<jsp:forward>`)
- **JavaBeans** for encapsulating business logic
- **HttpSession** for cart persistence
- **Cookies** for "Remember Me" login
- **JDBC + Oracle XE** for data persistence
- **ServletContext + Servlet init()** for application-wide setup
- **Properties file loading** for externalized DB config


## ✨ Features

- 👤 **User registration & login** with JDBC-backed validation
- 🍪 **Remember Me** using persistent cookies (`LoginData.jsp`)
- 🛒 **Session-based cart** — add products across 7 categories
- 📱 **7 product categories**: Mobiles, Laptops, Cars, Watches, Pendrives, Calculators, and more
- 💰 **Cart page** with per-category totals and grand total
- 🖼️ **Product image viewer** (`image.jsp`)
- 🚪 **Logout** with session invalidation
- 🗄️ **Auto schema creation** on app startup via `ApplicaionInitializer` servlet
- ⚙️ **Externalized config** via `db.properties` loaded at init time
- 🔐 **Session guard** — pages forward to login if session is null


## 🛠️ Tech Stack

| Layer | Technology |
|-------|-----------|
| Language | Java (JDK 8) |
| Web | JSP 2.x, Servlets, JavaBeans |
| Database | Oracle XE (via JDBC Thin driver) |
| Server | Oracle WebLogic Server 12c |
| Config | `web.xml` + `db.properties` |
| Architecture | JSP Model 1 with JavaBeans |


## 🗄️ Database Schema

Auto-created on startup from `tables.txt`:

```sql
create table form(name VARCHAR2(20), pass VARCHAR2(20))
```

Product catalog is stored client-side (prices hardcoded in JSP hidden fields), so only user credentials persist.


## 🧠 Key Concepts Demonstrated

- **JSP Model 1 MVC** — JSPs as both view and controller; JavaBeans as model
- **JSP Standard Actions** — `<jsp:useBean>`, `<jsp:setProperty>`, `<jsp:forward>`
- **HttpSession** for cart state across 7 category pages
- **Cookie-based persistent login** — cookies read on `Login.jsp` and re-populated in `Login1.jsp`
- **Servlet init() + ServletContext** for one-time startup work
- **Properties file loading** into `System.setProperty()` for global config
- **JDBC with Oracle Thin driver** for auth persistence
- **Session guard pattern** — every secured JSP checks `session != null` and forwards to `front.jsp`


## 🚀 Future Enhancements

- [ ] Refactor to **JSP Model 2 (MVC)** with servlet controllers + JSP views only
- [ ] Add **JSTL** to replace scriptlets
- [ ] Replace hardcoded prices with **DB-backed product catalog**
- [ ] Add **admin panel** for product management
- [ ] Implement **order history** and payment simulation
- [ ] Migrate to **Spring MVC** or **Spring Boot**
- [ ] Add **password hashing** (BCrypt) — currently stored plaintext
- [ ] Add **JUnit tests** for `LoginBean` and `RegisterBean`


## ⚠️ Known Limitations

- Passwords stored as **plaintext** in Oracle — should be hashed
- Uses **JSP scriptlets** — modern approach uses JSTL or a template engine
- **SQL injection risk** — `LoginBean` builds SQL via string concatenation; should use `PreparedStatement`


## 👩‍💻 Author

**Yashdeep Kaur**
- 🎓 B.Tech CSE, Punjabi University, Patiala (2026)
- 💼 Java Full Stack Trainee @ CodeSquadz
- 📧 ykdeep2453@gmail.com
- 🔗 [LinkedIn](https://linkedin.com/in/yashdeep-kaur-16aa083b1)
- 🐙 [@YashdeepKaur28](https://github.com/YashdeepKaur28)


⭐ If you found this useful, consider giving it a star!
