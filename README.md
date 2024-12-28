# EX01 Developing a Simple Webserver
## Date:26.10.2024

## AIM:
To develop a simple webserver to serve html pages and display the configuration details of laptop.

## DESIGN STEPS:
### Step 1: 
HTML content creation.

### Step 2:
Design of webserver workflow.

### Step 3:
Implementation using Python code.

### Step 4:
Serving the HTML pages.

### Step 5:
Testing the webserver.

## PROGRAM:
```
from http.server import HTTPServer,BaseHTTPRequestHandler

content='''
<!doctype html>
<html>
    <body bgcolor="dodger blue4">
        <table border="5" cellpadding="22" aling="center" bgcolor="cyan">
            <caption aling="center">LAPTOP CONFIGURATION </caption>
       
        <tr bgcolor="#56ASEC">
            <th>S.NO</th><th>SYSTEM CONFIGURATION</th><th>DESCRIPTION</th>
        </tr>
        <tr>
            <th>1</th><th>PROCESSOR</th><th>i5</th>
        </tr>
        <tr>
            <th>2</th><th>PRIMARY MEMORY</th><th>RAM 16GB</th>
        </tr>
        <TR>
            <th>3</th><th>SECONDARY MEMORY</th><th>512 GB</th>
        </TR>
        <tr>
            <th>4</th><th>OS</th><th>WINDOWS 10</th>
        </tr>
        <tr>
            <th>5</th><th>display</th><TH>40cms</TH>
            </tr>


'''

class MyServer(BaseHTTPRequestHandler):
    def do_GET(self):
        print("Get request received...")
        self.send_response(200) 
        self.send_header("content-type", "text/html")       
        self.end_headers()
        self.wfile.write(content.encode())

print("This is my webserver") 
server_address =('',8000)
httpd = HTTPServer(server_address,MyServer)
httpd.serve_forever()
```

## OUTPUT:

![alt text](IMG-20241026-WA0016.jpg)
![alt text](<Screenshot (236).png>)


## RESULT:
The program for implementing simple webserver is executed successfully.
