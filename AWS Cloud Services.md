### Amazon EC2 Service (Amazon Compute Cloud):
* Commands to host a static website via EC2 Instance connect terminal
  ```
  sudo su - (navigate as a root user from ec2-user)
  yum update -y
  yum install -y httpd (httpd --> Apache server, http server)
  systemctl status httpd
  mkdir temp
  cd temp
  wget https://github.com/Padmavathi-SJ/demo-app/archive/refs/heads/main.zip
  ls -lrt
  unzip main.zip
  cd demo-app-main
  mv * /var/www/html/
  cd /var/www/html/
  ls -lrt
  systemctl enable httpd
  systemctl start httpd
  ```
  
