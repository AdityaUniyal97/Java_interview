
### **Data vs Information**
- **Data** → Raw, unprocessed facts (numbers, text, images, sound).
- **Information** → Processed/organized data that has meaning.
### **Database**
- A **container to store related data**.
- **Types**:
    - **Structured** → Organized in rows & columns (RDBMS, e.g., IRCTC).
    - **Unstructured** → No fixed format (e.g., web pages with text, images).
### **DBMS (Database Management System)**
- Software to manage databases and perform **CRUD** operations (Create, Read, Update, Delete).
- Examples: MySQL, Oracle, SQL Server.
**Advantages:** Data sharing, security, reduced redundancy.  
**Disadvantages:** Costly, complex, needs maintenance.
### **File System vs DBMS**
- **File System** → Data in files/folders, high redundancy, weak security, slower search.
- **DBMS** → Data in structured database, less redundancy, strong security, faster search.
### **DBMS Architecture**
- **1-Tier** → User directly accesses database.
- **2-Tier** → Client ↔ Database (simple, fast, less secure).
- **3-Tier** → Client ↔ Application Server ↔ Database (secure, scalable, used in large apps).
### **Data Abstraction**
- Hides complexity, shows only necessary details.
- **Levels**:
    - **Physical** → How data is stored (storage, indexing).
    - **Logical** → What data is stored & relationships.
    - **View** → User-specific view.
### **Database Schemas**
- Blueprint/structure of the database.
- **Physical Schema** → Storage details.
- **Logical Schema** → Logical structure (tables, relations).
### **Types of Database Users**

1. **Database Administrator (DBA)** – Maintains the database (security, backups, performance, troubleshooting).
2. **End Users** – Use applications to access data.
    - Naive (predefined tasks, e.g., booking tickets)
    - Casual (occasional queries, e.g., managers)
    - Power (complex queries, e.g., analysts)
3. **Application Programmers** – Develop applications that interact with the database (queries, transactions).
4. **System Analysts** – Bridge business needs and technical design (schemas, requirements).
5. **Data Scientists/Analysts** – Extract insights, analyze, and visualize data for decision-making.