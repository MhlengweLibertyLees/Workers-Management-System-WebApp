
# 👷 Workers Management System WebApp

A Java EE web application designed to manage worker information using **Servlets**, **JSPs**, and **JPA (Java Persistence API)**. The system supports **CRUD operations** and allows users to manage the following worker details:

- ID Number  
- First Name  
- Last Name  
- Email  
- Gender  
- Job Title  
- Date Hired  

---

## 🚀 Features

- Create new worker entries  
- View all workers in a structured table  
- Update worker details  
- Delete a worker  
- Automatically persists data using JPA to a JavaDB (Derby) database  

---

## 🖥️ Technologies Used

- Java EE (Servlets + JSP)  
- JPA (Java Persistence API)  
- GlassFish Server  
- JavaDB (Apache Derby)  
- NetBeans IDE  

---

===================================================================================================
🛠 How to Run
1. Clone the Repository
bash
Copy
Edit
git clone https://github.com/MhlengweLibertyLees/workers-management-system.git

3. Open in NetBeans
Open NetBeans IDE.

Go to File > Open Project, then navigate to the cloned folder and open the project.

3. Set Up the Database (JavaDB)
Open the Services tab in NetBeans.

Expand Databases > JavaDB.
Right-click and choose Create Database:

Database name: WorkersDb
User name: app
Password: 123

Right-click the new database and choose Connect.

4. Verify persistence.xml
Ensure your persistence.xml file is located in src/META-INF/ and contains the following configuration:

xml
Copy
Edit
<persistence-unit name="WorkersPU" transaction-type="RESOURCE_LOCAL">
    <provider>org.eclipse.persistence.jpa.PersistenceProvider</provider>
    <class>model.Worker</class>
    <properties>
        <property name="javax.persistence.jdbc.url" value="jdbc:derby://localhost:1527/WorkersDb"/>
        <property name="javax.persistence.jdbc.user" value="app"/>
        <property name="javax.persistence.jdbc.password" value="123"/>
        <property name="javax.persistence.jdbc.driver" value="org.apache.derby.jdbc.ClientDriver"/>
        <property name="eclipselink.ddl-generation" value="create-tables"/>
    </properties>
</persistence-unit>
5. Deploy on GlassFish
Make sure GlassFish Server is added to NetBeans under Tools > Servers.

Right-click your project and choose Run or Deploy.

6. Access the Web Application
Once deployed, open your browser and go to:

http://localhost:8080/WorkersManagementSystem

