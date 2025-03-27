# EX01 Developing a Simple Webserver

# Date:27.03.2025
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
from http.server import HTTPServer, BaseHTTPRequestHandler
content = """

<html lang="en">
<body>
<heading>
<h1><b>barkavi</b></h1>
<h2>CONFIGURATION:24901000</h2>
<ol> 
 <li>Device name	DESKTOP-MOHHBTU</li>
 <li>Processor	13th Gen Intel(R) Core(TM) i5-1335U   1.30 GHz</li>
 <li>Installed RAM	16.0 GB (15.7 GB usable)</li>
 <li>Device ID	15EEA3B2-7EF5-4DEC-903D-577382C3C005</li>
 <li>Product ID	00342-42709-15956-AAOEM</li>
 <li><i>System type	64-bit operating system, x64-based processor</i></li>
 <li>Pen and touch	No pen or touch input is available for this display</li>
</ol>
</body>
</html>

"""
class myhandler(BaseHTTPRequestHandler):
    def do_GET(self):
        print("request received")
        self.send_response(200)
        self.send_header('content-type', 'text/html; charset=utf-8')
        self.end_headers()
        self.wfile.write(content.encode())
server_address = ('',8000)
httpd = HTTPServer(server_address,myhandler)
print("my webserver is running...")
httpd.serve_forever()
```
# OUTPUT:
![Screenshot (203)](https://github.com/user-attachments/assets/1a16fc95-0090-42bb-94a1-596e09ece6bb)
![Screenshot (204)](https://github.com/user-attachments/assets/8c4f3460-32c7-4017-a33e-e02e0a9e9867)



# RESULT:
The program for implementing simple webserver is executed successfully.
