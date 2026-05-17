![[Pasted image 20260202121736.png]]

![[Pasted image 20260202122248.png]]


# What is URLConnection?

`URLConnection` is used to **establish communication between the Java program and a URL resource**.


A **Servlet** is a Java program that runs on a **web server** and handles requests from web browsers.

![[Pasted image 20260313091258.png]]

![[Pasted image 20260313091607.png]]


JDBC DRIVERS 

| Type   | Name                    |
| ------ | ----------------------- |
| Type 1 | JDBC-ODBC Bridge Driver |
| Type 2 | Native API Driver       |
| Type 3 | Network Protocol Driver |
| Type 4 | Thin Driver             |
![[Pasted image 20260313092718.png]]
### 1. JDBC-ODBC Bridge Driver - Type 1 Driver

Type-1 driver or JDBC-ODBC bridge driver uses ODBC driver to connect to the database. The JDBC-ODBC bridge driver converts JDBC method calls into the ODBC function calls. Type-1 driver is also called Universal driver because it can be used to connect to any of the databases.

![[Pasted image 20260313092725.png]]
### ****.**** Native-API Driver - Type 2 Driver ( Partially Java Driver)

The Native API driver uses the client -side libraries of the database. This driver converts JDBC method calls into native calls of the database API. In order to interact with different database, this driver needs their local API, that's why data transfer is much more secure as compared to type-1 driver. This driver is not fully written in Java that is why it is also called Partially Java driver.


![[Pasted image 20260313092732.png]]
### Network Protocol Driver - Type 3 Driver (Fully Java Driver)

The Network Protocol driver uses middleware (application server) that converts JDBC calls directly or indirectly into the vendor-specific database protocol. Here all the database connectivity drivers are present in a single server, hence no need of individual client-side installation.



![[Pasted image 20260313092739.png]]

###  Thin Driver - Type 4 Driver (Fully Java Driver)

Type-4 driver is also called native protocol driver. This driver interact directly with database. It does not require any native database library, that is why it is also known as Thin Driver.



![[Pasted image 20260313105622.png]]

| Feature       | GET           | POST         |
| ------------- | ------------- | ------------ |
| Purpose       | Retrieve data | Send data    |
| Data Location | URL           | Request body |
| Security      | Less secure   | More secure  |
| Data Size     | Limited       | Large        |
| Bookmark      | Possible      | Not possible |

| Feature  | Cookie       | Session            |
| -------- | ------------ | ------------------ |
| Storage  | Browser      | Server             |
| Security | Less secure  | More secure        |
| Size     | Small        | Larger             |
| Lifetime | Until expiry | Until session ends |

### 1. PreparedStatement (The Speedster)

**Think of it as:** A reusable template.

- **The Logic:** Instead of sending a full SQL command every time, you send a template with placeholders (`?`). The database compiles it once.
    
- **Why use it?** It’s faster for loops and prevents **SQL Injection** (hackers putting code in your input boxes) because the "structure" is already fixed.
    

### 2. CallableStatement (The Remote Control)

**Think of it as:** A button that triggers a program already sitting on the Database server.

- **The Logic:** It's used to call **Stored Procedures**.
    
- **Why use it?** If the database has a complex 50-step process (like "Calculate Monthly Interest"), you don't want to write that in Java. You just call the "Interest" procedure.

![[Pasted image 20260313102831.png]]
### 1. GenericServlet vs. HttpServlet

- **GenericServlet:** The "Base Model." It doesn't care if you're using HTTP, FTP, or SMTP. It just knows how to "serve." You have to write the logic inside one big `service()` method.
    
- **HttpServlet:** The "Upgrade." It’s built specifically for the web (HTTP). It knows the difference between a **GET** (asking for data) and a **POST** (submitting data).
    

### 2. ServletConfig vs. ServletContext

- **ServletConfig : is an object that contains initialization parameters for a specific servlet. It is created by the servlet container and passed to the servlet during initialization.

- Defined inside <servlet> in web.xml
- Each servlet has its own ServletConfig object
 Accessed using getServletConfig()

    
- **ServletContext (The Building Manager):** is an object that holds application-wide configuration information. It is shared among all servlets in the web application.

- Application-wide configuration
- Defined using <context-param> in web.xml
- Only one ServletContext object per application
- Accessed using getServletContext()




# Banking app code

```
import java.sql.*; // 1. Always import the SQL package

public class BankAdmin {
    public static void main(String[] args) {
        try {
            // STEP 1: Register the driver (The "Translator")
            Class.forName("com.mysql.cj.jdbc.Driver");

            // STEP 2: Connect to the DB (The "Phone Call")
            Connection con = DriverManager.getConnection("jdbc:mysql://localhost:3306/bankDB", "root", "password");

            // STEP 3: Create a Statement (The "Messenger")
            Statement stmt = con.createStatement();

            // STEP 4: The UPDATE (Action)
            // Use executeUpdate for things that CHANGE the data (Insert, Update, Delete)
            String updateQuery = "UPDATE bank SET Address = 'Mumbai' WHERE AccountNo = 1001";
            int rowsAffected = stmt.executeUpdate(updateQuery);
            System.out.println(rowsAffected + " record updated successfully.");

            // STEP 5: The DISPLAY (Reading)
            // Use executeQuery for things that READ data (Select)
            String selectQuery = "SELECT * FROM bank";
            ResultSet rs = stmt.executeQuery(selectQuery);

            System.out.println("AccNo | Name | Phone | Address");
            while (rs.next()) {
                // rs.getXXX reads the column by its name or index
                System.out.println(rs.getInt("AccountNo") + " | " + 
                                   rs.getString("CustomerName") + " | " + 
                                   rs.getString("Address"));
            }

            // STEP 6: Close (The "Goodbye")
            con.close();

        } catch (Exception e) {
            e.printStackTrace(); // Always catch errors to see what went wrong
        }
    }
}
```

prime bumber

```
import java.io.*;
import javax.servlet.*;
import javax.servlet.http.*;

public class PrimeServlet extends HttpServlet {
    // doGet or doPost handles the request
    public void doGet(HttpServletRequest request, HttpServletResponse response) 
            throws ServletException, IOException {
        
        response.setContentType("text/html"); // Tell the browser we are sending HTML
        PrintWriter out = response.getWriter(); // The "Pen" to write on the web page

        // Grab the numbers from the URL/Form
        int n1 = Integer.parseInt(request.getParameter("num1"));
        int n2 = Integer.parseInt(request.getParameter("num2"));

        out.println("<h3>Prime numbers between " + n1 + " and " + n2 + ":</h3>");

        for (int i = n1; i <= n2; i++) {
            if (isPrime(i)) {
                out.print(i + " ");
            }
        }
    }

    // Logic: A prime is only divisible by 1 and itself
    private boolean isPrime(int n) {
        if (n < 2) return false;
        for (int i = 2; i <= Math.sqrt(n); i++) {
            if (n % i == 0) return false;
        }
        return true;
    }
}

```

xml 
```
<web-app>
    <servlet>
        <servlet-name>MyPrimeLogic</servlet-name> <servlet-class>PrimeServlet</servlet-class> </servlet>

    <servlet-mapping>
        <servlet-name>MyPrimeLogic</servlet-name> <url-pattern>/findPrimes</url-pattern> </servlet-mapping>
</web-app>
```



```
import java.sql.*;

public class InventoryManager {
    public static void main(String[] args) {
        try {
            // 1. Connection setup (The standard "Handshake")
            Class.forName("com.mysql.cj.jdbc.Driver");
            Connection con = DriverManager.getConnection("jdbc:mysql://localhost:3306/inventoryDB", "root", "password");
            Statement stmt = con.createStatement();

            // 2. DELETE OLD PRODUCTS (The "Cleanup")
            // We do this first so the expired items don't show up in our list
            String deleteSQL = "DELETE FROM Product WHERE Pro_Exp_year = 2022";
            int deletedCount = stmt.executeUpdate(deleteSQL);
            System.out.println("Cleaned up " + deletedCount + " expired products.");

            // 3. DISPLAY ALL RECORDS (The "Inventory Check")
            String selectSQL = "SELECT * FROM Product";
            ResultSet rs = stmt.executeQuery(selectSQL);

            System.out.println("ID | Name | MNF | EXP | Price");
            while (rs.next()) {
                // Get data by column name
                int id = rs.getInt("Prod_id");
                String name = rs.getString("Prod_name");
                int expYear = rs.getInt("Pro_Exp_year");
                double price = rs.getDouble("Prod_price");
                
                System.out.println(id + " | " + name + " | " + expYear + " | $" + price);
            }

            con.close();
        } catch (Exception e) {
            System.out.println("Error: " + e.getMessage());
        }
    }
}
```



```
import java.io.*;
import javax.servlet.*;
import javax.servlet.http.*;

public class WelcomeServlet extends HttpServlet {
    public void doPost(HttpServletRequest req, HttpServletResponse res) 
            throws IOException, ServletException {
        
        res.setContentType("text/html");
        PrintWriter out = res.getWriter();

        // 1. Grab the name from the form
        String name = req.getParameter("user_name");

        // 2. Validation Logic
        if (name != null && !name.trim().isEmpty()) {
            out.println("<h1>Welcome " + name + "</h1>");
        } else {
            out.println("<h1>Invalid Username!</h1>");
        }
    }
}
```

xml 
```
<servlet>
    <servlet-name>WS1</servlet-name>
    <servlet-class>WelcomeServlet</servlet-class>
</servlet>
<servlet-mapping>
    <servlet-name>WS1</servlet-name>
    <url-pattern>/welcome</url-pattern> </servlet-mapping>
```