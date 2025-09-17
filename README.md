# EX01 Developing a Simple Webserver

# Date:17.09.2025
# AIM:
To develop a simple webserver to serve html pages and display the configuration details of laptop.

# DESIGN STEPS:
## Step 1:
HTML content creation.

## Step 2:
Design of webserver workflow.

## Step 3:
Implementation using Python code.

## Step 4:
Serving the HTML pages.

## Step 5:
Testing the webserver.

# PROGRAM:
```
from http.server import BaseHTTPRequestHandler, HTTPServer
content='''<html>
<h1>Configuration Details of Laptop</h1>
<h2>Device Specifications</h2>
<pre>Device name	LAPTOP-G3LIHLCT
Processor    	AMD Ryzen 7 7445HS w/ Radeon 740M Graphics      (3.20 GHz)
Installed RAM	16.0 GB (15.3 GB usable)
Device ID       E738BC7E-ED36-4A5B-9694-956E95B3A6F8
Product ID  	00342-42761-98599-AAOEM
System type     64-bit operating system, x64-based processor
Pen and touch	No pen or touch input is available for this display
</pre>
<h2>Windows Specifications</h2>
<pre>Edition	Windows 11 Home Single Language
Version	22H2   (OS Build 22621.1702)
Experience	Windows Feature Experience Pack 1000.22631.1000.0 
</pre>
<h2>Support</h2>
<p>Manufacturer	HP</p>


</html>'''
class myserver(BaseHTTPRequestHandler):
    def do_GET(self):
        self.send_response(200)
        self.send_header('Content-type', 'text/html')
        self.end_headers()
        self.wfile.write(content.encode())
print("This is my webserver")
server_address = ('', 8000)
httpd = HTTPServer(server_address, myserver)
httpd.serve_forever()
```
# OUTPUT:
![alt text](<Screenshot (6).png>)

# RESULT:
The program for implementing simple webserver is executed successfully.
