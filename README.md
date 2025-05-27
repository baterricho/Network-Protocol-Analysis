Web Application PIN Brute-Force Challenge
=========================================

Overview:
---------
This project is a Python script that guesses a web application's 3-digit PIN password by sending raw HTTP POST requests using only the socket library. The goal is to systematically try all combinations from 000 to 999 until the correct PIN is found.

Solution Process:
-----------------
1. Server Address and Port:
   - After running the provided executable (ctf1_for_x86.exe), I found the server listening at IP 172.20.10.3 on port 8888.

2. Communication with Server:
   - The server expects an HTTP POST request to /verify.
   - The body must include the parameter "magicNumber" with the PIN (example: magicNumber=123).
   - A successful PIN returns a response containing "Access Granted".

3. Handling Constraints:
   - The server introduces a delay after each attempt.
   - I added a 1.2 second delay (time.sleep(1.2)) between each request to avoid getting blocked.

4. Strategy:
   - Try all 3-digit combinations (000 to 999).
   - Send each PIN using raw sockets.
   - Detect success by checking if "Access Granted" appears in the response.
   - Stop when the correct PIN is found.

How to Run:
-----------
1. Start the web server by running the ctf1_for_x86.exe file.
2. Open a terminal or command prompt.
3. Run the Python script:
   python Client.py

Files Included:
---------------
- Client.py -> The Python brute-forcing script
- README.txt -> This documentation

