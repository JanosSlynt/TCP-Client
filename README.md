import socket

#Raw input for 'string'
#input for integer
target_host = raw_input("Target IP? ")
target_port = input("Target port? ")

client = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
client.connect((target_host,target_port))
client.send("GET / HTTP/1.1\r\nHost: google.com\r\n\r\n")
response = client.recv(4096)

print response
