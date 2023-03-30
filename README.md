# Developing a Simple Webserver

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
from http.server import HTTPServer,BaseHTTPRequestHandler

content='''
<!doctype html>
<html>
<head>
<title> My Web Server</title>
</head>
<body>
<h1>Top Five Web Application Development Frameworks</h1>
<h2>1. Django</h2>
<h2>2. MEAN Stack</h2>
<h2>3. React </h2>
<h2>4. Ruby on Rails </h2>
<h2>5. Spring </h2>

</body>
</html>
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

![out1](https://user-images.githubusercontent.com/119345345/228734414-0ede7749-6013-418e-afa3-d6c8996d2124.png)


### SERVER OUTPUT

![out2](https://user-images.githubusercontent.com/119345345/228734472-eb16d26f-f622-47a3-8890-2f8843833f8f.png)


## RESULT:
The program is executed succesfully
