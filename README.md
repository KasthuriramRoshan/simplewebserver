# EX01 Developing a Simple Webserver
## Date:28.09.2026

## AIM:
To develop a simple webserver to serve html pages and display the Windows Specifications of your Laptop.

## DESIGN STEPS:
### Step 1: 
HTML content creation.

### Step 2:
Design of webserver workflow.

### Step 3:
Implementation using Python code.

### Step 4:
Import the necessary modules.

### Step 5:
Define a custom request handler.

### Step 6:
Start an HTTP server on a specific port.

### Step 7:
Run the Python script to serve web pages.

### Step 8:
Serve the HTML pages.

### Step 9:
Start the server script and check for errors.

### Step 10:
Open a browser and navigate to http://127.0.0.1:8000 (or the assigned port).

## PROGRAM:
```
from http.server import HTTPServer, BaseHTTPRequestHandler
content = """
<html>
    <head>
        <title>Sample web page</title>
    </head>
    <body bgcolor="lightblue" align="center">
        <h1>Kasthuriram Roshan G B - 26018672</h1>
        <table border="1" cellpadding="10" cellspacing="10" align="center" bgcolor="lightblue">
            <caption>My Laptop Configuration</caption>
            <tr>
                <th>Sno</th>
                <th>Device Type</th>
                <th>Device Info</th>
            </tr>
            <tr>
                <td align="center">1.</td>
                <td>Device Name</td>
                <td>TL15-53M-G2</td>
            </tr>
            <tr>
                <td align="center">2.</td>
                <td>Processor</td>
                <td>Intel(R) Core(TM) 5 210H (2.20 GHz)</td>
            </tr>
            <tr>
                <td align="center">3.</td>
                <td>Installed RAM</td>
                <td>16.0 GB (15.7 GB usable)</td>
            </tr>
            <tr>
                <td align="center">4.</td>
                <td>Graphics Card</td>
                <td>Intel(R) Graphics (128 MB)</td>
            </tr>
             <tr>
                <td align="center">5.</td>
                <td>Storage</td>
                <td>113 GB of 477 GB used</td>
            </tr>
             <tr>
                <td align="center">6.</td>
                <td>Device Id</td>
                <td>BDBE9ACB-B12C-49AD-9241-51906F45209D</td>
            </tr>
             <tr>
                <td align="center">7.</td>
                <td>Product Id</td>
                <td>00342-42945-51970-AAOEM</td>
            </tr>
             <tr>
                <td align="center">8.</td>
                <td>System Type</td>
                <td>64-bit operating system, x64-based processor</td>
            </tr>
             <tr>
                <td align="center">9.</td>
                <td>Pen and Touch support</td>
                <td>No pen or touch input is available for this display</td>
            </tr>
        </table>
    </body>   
</html>
"""
class myhandler(BaseHTTPRequestHandler):
    def do_GET(self):
        print("Client request received")
        self.send_response(200)
        self.send_header('content-type', 'text/html; charset=utf-8')
        self.end_headers()
        self.wfile.write(content.encode())
server_address = ('',8000)
httpd = HTTPServer(server_address,myhandler)
print("my own webserver is running successfully...")
httpd.serve_forever()

```

## OUTPUT:
Webpage:
![alt text](<Screenshot (16).png>)

Serverpage:
![alt text](<Screenshot (17).png>)

## RESULT:
The program for implementing simple webserver is executed successfully.
