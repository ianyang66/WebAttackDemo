## WebAttackDemo

# Prerequest
* Install Docker  
Debian-series  
> sudo apt update  
sudo apt install -y docker.io  
sudo systemctl enable docker --now  
sudo usermod -aG docker $USER  

# Download
> git clone https://github.com/ianyang66/WebAttackDemo.git
# Build DockerImage
docker build -t webattackdemo .
## Vulnerabilities

* Reflected XSS  
http://localhost/pictures/search.php?query=blah  
The query parameter is vulnerable.  

* Stored XSS  
http://localhost/guestbook.php  
The comment field is vulnerable.  

* SessionID vulnerability  
http://localhost/admin/login.php  
The session cookie value is admin_session, which is an auto-incrementing value.  

* Stored SQL Injection  
http://localhost/users/register.php -> http://localhost/users/similar.php  
The first name field of the register users form contains a stored SQL injection which is then used unsanitized on the similar users page.  

* Reflected SQL Injection  
http://localhost/users/login.php  
The username field is vulnerable.  

* Directory Traversal  
http://localhost/pictures/upload.php  
The tag field has a directory traversal vulnerability enabling a malicious users to overwrite any file the web server uses has access to.  

* Multi-Step Stored XSS  
http://localhost/pictures/view.php?picid=3  
The comment field is vulnerable to XSS, however must go through a preview form.  

* Forceful Browsing  
http://localhost/pictures/highquality.php?picid=3&key=highquality  
The user doesn't have to purchase the picture to see the high quality version.

* Command-line Injection  
http://localhost/passcheck.php  
The password field is vulnerable to a command line injections.  

* File Inclusion  
http://localhost/admin/index.php?page=login  
The page is vulnerable to a file inclusion vulnerability, however you have to include %00 at the end.  

* Parameter Manipulation  
http://localhost/users/sample.php?userid=1  
The userid parameter can be manipulated to see any user's page when you need to be logged in otherwise.  

* Reflected XSS Behind JavaScript  
http://localhost/piccheck.php  
The name parameter is vulnerable.  

* Logic Flaw  
http://localhost/cart/review.php  
A coupon can be applied multiple times reducing the price of an order to zero. The coupon in the initial data is SUPERYOU21.  

* Reflected XSS Behind a Flash Form  
http://localhost/submitname.php  
The value parameter is vulnerable.  

* Weak username/password  
https://localhost/admin/login.php  
There is a default username/password combination of admin/admin.  

