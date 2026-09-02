# Sqlinjection
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
<img width="720" height="400" alt="1" src="https://github.com/user-attachments/assets/9228215e-7d2d-42e3-b292-19733ee0df44" />


Use the above ip address to access the apache webserver of Metasploitable2 from kali linux. In Kali Linux use the ip address in a web browser.
## OUTPUT:
<img width="1920" height="1200" alt="2" src="https://github.com/user-attachments/assets/98a1377a-9fe6-4780-bc81-bde348a55bb2" />


Select Multidae from the menu listed as shown above. You will get the page as displayed below:
## OUTPUT:
<img width="1920" height="1200" alt="3" src="https://github.com/user-attachments/assets/d1903707-d71b-46d4-9b3b-98ce4aaac383" />


Click on the menu Login/Register and register for an account
## OUTPUT:
<img width="1920" height="1200" alt="4" src="https://github.com/user-attachments/assets/f73af6d5-cee0-4db1-b6c7-0d56a1e2277d" />



Click on “Create Account” to display the following page:
## OUTPUT:




The login structure we will use in our examples is straightforward. It contains two input fields (username and password), which are both vulnerable. The back-end content creates a query to approve the username and secret key given by the client. Here is an outline of the page rationale:

($query = “SELECT * FROM users WHERE username=’$_POST[username]’ AND password=’$_POST[password]’“;). For the username put “ganesh” or “anything” and for the password put (anything’ or ‘1’=’1) or (admin’ or ‘1’=’1) then try to log in, and you’ll be presented with an admin login page. Click “Login”. 
## OUTPUT:
<img width="1920" height="1200" alt="5" src="https://github.com/user-attachments/assets/881ed7dc-bbbd-446b-8457-8be3a05b1836" />

## Bypassing login field

The username field is vulnerable. Put (blaise’ #) or (blaise’--) in the username field and hit “Enter” to log in. We use “#” or “--” to comment everything in the query sentence that comes after the username filed telling the database to disregard the password field: (SELECT * FROM users WHERE username=’admin’ # AND password=’ ‘). By using line commenting, the aggressor eliminates a part of the login condition and gains access. This technique will make the “WHERE” clause true only for one user; in this case, it is “blaise.”
Now after logging out you will see the login page. In the login page give blaise’ # . You can see the page now enters into the administrator page as before when giving the password.
## OUTPUT:
<img width="1920" height="1200" alt="6" src="https://github.com/user-attachments/assets/d5d2fe7f-e7f5-472d-b0d9-2c5943077812" />

Click the login button and you will see it enter into the administrator page
## OUTPUT:
<img width="1920" height="1200" alt="7" src="https://github.com/user-attachments/assets/ecb53eb2-1ed6-4ffb-b58f-83d6527831e8" />

## Union-based SQL injection
UNION-based SQL injection assaults enable the analyzer to extract data from the database effectively. Since the “UNION” operator must be utilized if the two inquiries have precisely the same structure, the attacker must craft a “SELECT” statement like the first inquiry. we will be using the “User Info” page from Mutillidae to perform a Union-Based SQL injection attack. Go to “OWASP Top 10/A1 — Injection/SQLi — Extract-Data/User Info”

After logging out, Now choose the menu as shown below:
The SQL Injection vulnerability is successfully exploited using the Multidae web application in Metasploitable2.
