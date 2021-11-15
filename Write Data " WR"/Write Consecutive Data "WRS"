import socket
from time import sleep
print('Start')
HOST = '169.254.98.140'  # Standard loopback interface address (localhost)
PORT = 8501        # Port to listen on (non-privileged ports are > 1023)
print('Wait')
with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as s:
    s.connect((HOST, PORT))
    while True:
        cmd = "WR {}{} {}\r\n".format("DM102", ".U", "1")
        print('send', repr(cmd))
        s.sendall(cmd.encode())
        data = s.recv(1024)
        print('Received', repr(data))
        sleep(1)
        cmd = "WR {}{} {}\r\n".format("DM102", ".U", "3")
        print('send', repr(cmd))
        s.sendall(cmd.encode())
        data = s.recv(1024)
        print('Received', repr(data))
        sleep(1)
