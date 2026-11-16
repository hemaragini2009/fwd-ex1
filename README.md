# EX01 Developing a Simple Webserver
## Date:

## AIM:
To develop a simple webserver to serve html pages and display the list of protocols in TCP/IP Protocol Suite.

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
from http.server import HTTPServer, BaseHTTPRequestHandler
content = """
<!DOCTYPE html>
<html>
<head>
    <title>TCP/IP Protocol Suite</title>

    <style>
        body {
            font-family: Arial, sans-serif;
            background: linear-gradient(120deg, #dbeafe, #ede9fe);
            margin: 0;
            padding: 20px;
        }

        h1 {
            text-align: center;
            color: #312e81;
        }

        .subtitle {
            text-align: center;
            color: #475569;
        }

        .container {
            max-width: 850px;
            margin: auto;
        }

        .layer {
            background: white;
            margin: 20px 0;
            padding: 20px;
            border-radius: 15px;
            box-shadow: 0 4px 10px #0002;
            border-left: 8px solid #6366f1;
        }

        h2 {
            color: #4338ca;
        }

        ul {
            display: flex;
            flex-wrap: wrap;
            gap: 12px;
            padding: 0;
            list-style: none;
        }

        li {
            background: #e0e7ff;
            padding: 12px 18px;
            border-radius: 10px;
            color: #312e81;
            font-weight: bold;
        }

        li:hover {
            background: #6366f1;
            color: white;
            transform: scale(1.05);
        }

        footer {
            text-align: center;
            margin-top: 30px;
            color: #475569;
        }
    </style>
</head>

<body>

    <h1>🌐 TCP/IP Protocol Suite</h1>
    <p class="subtitle">
        Explore the four layers of Internet Communication
    </p>

    <div class="container">

        <div class="layer">
            <h2>📱 1. Application Layer</h2>
            <p>Provides network services directly to user applications.</p>
            <ul>
                <li>HTTP</li>
                <li>HTTPS</li>
                <li>FTP</li>
                <li>SMTP</li>
                <li>DNS</li>
                <li>DHCP</li>
                <li>SSH</li>
                <li>POP3</li>
                <li>IMAP</li>
            </ul>
        </div>

        <div class="layer">
            <h2>🚚 2. Transport Layer</h2>
            <p>Provides end-to-end communication between devices.</p>
            <ul>
                <li>TCP</li>
                <li>UDP</li>
            </ul>
        </div>

        <div class="layer">
            <h2>🌍 3. Internet Layer</h2>
            <p>Handles logical addressing and packet routing.</p>
            <ul>
                <li>IP (IPv4)</li>
                <li>IP (IPv6)</li>
                <li>ICMP</li>
                <li>IGMP</li>
            </ul>
        </div>

        <div class="layer">
            <h2>🔌 4. Network Access Layer</h2>
            <p>Responsible for transmitting data through the physical network.</p>
            <ul>
                <li>Ethernet</li>
                <li>Wi-Fi (IEEE 802.11)</li>
                <li>ARP</li>
                <li>PPP</li>
            </ul>
        </div>

    </div>

    <footer>
        <p>✨ Learn • Connect • Communicate ✨</p>
        <p>TCP/IP – The Foundation of Internet Communication</p>
    </footer>

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
server_address = ('',880)
httpd = HTTPServer(server_address,myhandler)
print("my webserver is running...")
httpd.serve_forever()


## OUTPUT:
<img width="1252" height="972" alt="Screenshot 2026-11-14 160049" src="https://github.com/user-attachments/assets/6acebf46-fff2-45e3-8190-2d7339f31d5d" />
<img width="1207" height="418" alt="Screenshot 2026-11-14 160114" src="https://github.com/user-attachments/assets/f3a9849e-d179-4673-a172-e343b9194f24" />
<img width="1050" height="268" alt="Screenshot 2026-11-14 160146" src="https://github.com/user-attachments/assets/821974e8-0ca3-4c75-bd45-3511342e077b" />





## RESULT:
The program for implementing simple webserver is executed successfully.

