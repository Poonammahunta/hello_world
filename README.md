19# hello_world
import paramiko
ssh = paramiko.SSHClient()

##setting up ip,hostname,port,user details
ip = "192.168.1.8"
port = 22
username = "poo"
password = "hagideli"
ssh.set_missing_host_key_policy(paramiko.AutoAddPolicy())
ssh.connect(ip,port,username,password)
stdin,stdout,stderr=ssh.exec_command("df -hT")
outlines=stdout.readlines()
resp=''.join(outlines)
print(resp)
