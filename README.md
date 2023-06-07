# Ex01 Developing a Simple Webserver

# AIM:

To develop a simple webserver to serve html programming pages.

## DESIGN STEPS:

### Step 1:

HTML content creation is done

### Step 2:

Design of webserver workflow

### Step 3:

Implementation using Python code

### Step 4:

Serving the HTML pages.

### Step 5:

Testing the webserver

## PROGRAM:
```
from http.server import HTTPServer, BaseHTTPRequestHandler
content = """
<!DOCTYPE html>
<html>
<head>
<title>My webserver</title>
</head>
<body>
<h1><u>Languages used in Web Development</u><h1>
<ul>
<li>HTML</li>
<li>CSS</li>
<li>JavaScript</li>
<li>Bootstrap</li>
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
server_address = ('',80)
httpd = HTTPServer(server_address,myhandler)
print("my webserver is running...")
httpd.serve_forever()
```
## OUTPUT:
## SERVER OUTPUT:
![WhatsApp Image 2023-06-07 at 11 52 20 AM](https://github.com/Kalpanareshma/webserver/assets/122040453/be7cf5fd-c31b-4f2c-81e8-e39d02974a8a)
## CLIENT OUTPUT:
![EX-01 WEB](https://github.com/Kalpanareshma/webserver/assets/122040453/86e2dcaa-9e0a-4063-8c20-28a91609f6b9)

## RESULT:
The program is executed succesfully.
