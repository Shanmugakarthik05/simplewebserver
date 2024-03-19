# EX01 Developing a Simple Webserver
## Date:23.2.2024

## AIM:
To develop a simple webserver to serve html pages.

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
~~~
from http.server import HTTPServer, BaseHTTPRequestHandler
content = """

<html>

<head>
       <title> Software companies revenue</title>
</head>

<body>
<table align="center" border="4" cellspacing="5" cellpadding="4" height="200" width="250">

<caption> Top 5 software companies </caption>

<tr>
    <th>Rank</th>
    <th>Company name</th>
    <th>Revenue</th>

</tr>

<tr>
    <td>1</td>
    <td>Microsoft</td>
    <td>$65.7b</td>
</tr>
<tr>
    <td>2</td>
    <td>Oracle</td>
    <td>$29.6</td>

</tr>
<tr>
    <td>3</td>
    <td>IBM</td>
    <td>$29.1</td>
</tr>

<tr>
    <td>4</td>
    <td>SAP</td>
    <td>$18.5b</td>

</tr>

<tr>
    <td>5</td>
    <td>Symantec</td>
    <td>$6.4b</td>
</tr>

</table>

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
~~~

## OUTPUT:
![alt text](<Screenshot 2024-03-19 135304.png>)

![alt text](<Screenshot 2024-03-19 135412.png>)
## RESULT:
The program for implementing simple webserver is executed successfully.
