# WebAttackDemo

## Prerequest
* Install Docker  
-- Debian-series  
> sudo apt update  
	sudo apt install -y docker.io  
	sudo systemctl enable docker --now  
	sudo usermod -aG docker $USER  

## Download
	git clone https://github.com/ianyang66/WebAttackDemo.git

## Build DockerImage
	docker build -t webattackdemo .

## Run Docker Container
	docker run -p 127.0.0.1:8080:80 -it webattackdemo

## Vulnerabilities
* Reflected XSS  
http://localhost/pictures/search.php?query=blahblah  
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

