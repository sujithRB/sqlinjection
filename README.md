# sqlinjection
Exploiting SQL Injection vulnerability

# AIM:
To exploit SQL Injection vulnerability using Multidae web application in Metasploitable2

## DESIGN STEPS:

### Step 1:

Install kali linux either in partition or virtual box or in live mode


### Step 2:

Investigate on the various categories of tools as follows:

### Step 3:

Open terminal and try execute some kali linux commands

## EXECUTION STEPS AND ITS OUTPUT:
SQL Injection is a sort of infusion assault that makes it conceivable to execute malicious SQL statements. These statements control a database server behind a web application. Assailants can utilize SQL Injection vulnerabilities to sidestep application safety efforts. They can circumvent authentication and authorization of a page or web application and recover the content of the whole SQL database. 
Identify IP address using ifconfig in Metasploitable2
## OUTPUT:
![image](https://github.com/user-attachments/assets/dbc4ccb5-0390-4213-842f-000f34b81446)


Use the above ip address to access the apache webserver of Metasploitable2 from kali linux. In Kali Linux use the ip address in a web browser.
## OUTPUT:
![image](https://github.com/user-attachments/assets/5127eae7-18f2-4be5-84c9-589e466ac274)


Select Multidae from the menu listed as shown above. You will get the page as displayed below:
## OUTPUT:
![image](https://github.com/user-attachments/assets/3dcda901-1cc3-45e6-9992-687e0251e870)


Click on the menu Login/Register and register for an account
## OUTPUT:
![image](https://github.com/user-attachments/assets/0171ed31-4639-4b1a-9f3c-247631112ba4)



Click on “Create Account” to display the following page:
## OUTPUT:




The login structure we will use in our examples is straightforward. It contains two input fields (username and password), which are both vulnerable. The back-end content creates a query to approve the username and secret key given by the client. Here is an outline of the page rationale:

($query = “SELECT * FROM users WHERE username=’$_POST[username]’ AND password=’$_POST[password]’“;). For the username put “ganesh” or “anything” and for the password put (anything’ or ‘1’=’1) or (admin’ or ‘1’=’1) then try to log in, and you’ll be presented with an admin login page. Click “Login”. 
## OUTPUT:
![{BEC6843A-A0F1-4B48-A1FC-98E701497780}](https://github.com/user-attachments/assets/17f2ddcb-829b-4fb0-a8c0-a2532e8e2d2c)

## Bypassing login field

The username field is vulnerable. Put (blaise’ #) or (blaise’--) in the username field and hit “Enter” to log in. We use “#” or “--” to comment everything in the query sentence that comes after the username filed telling the database to disregard the password field: (SELECT * FROM users WHERE username=’admin’ # AND password=’ ‘). By using line commenting, the aggressor eliminates a part of the login condition and gains access. This technique will make the “WHERE” clause true only for one user; in this case, it is “blaise.”
Now after logging out you will see the login page. In the login page give blaise’ # . You can see the page now enters into the administrator page as before when giving the password.
## OUTPUT:
The SQL Injection vulnerability is successfully exploited using the Multidae web application in Metasploitable2.
