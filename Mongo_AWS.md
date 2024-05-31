# Install mongoDB on AWS ec2

### Go to ssh from terminal
```bash
cd .ssh
```
### Connect with your virtual computer(ec2)
```bash
ssh -i "your----.pem" ubuntu@ec0-00-0000.eu-central-1.compute.amazonaws.com
```
### Install MongoDB
follow the steps for installation
```bash
https://www.mongodb.com/docs/manual/tutorial/install-mongodb-on-ubuntu/
```

### Config issue
```bash
sudo nano /etc/ssh/sshd_config
```
```commandline
press : 'i'
change bindIP : 0.0.0.0
security : authorization: enabled
press : 'esc' on your key board
type : Ctrl + o
type : Ctrl + x
```

### Save file and end mongodb 
```bash
sudo systemctl restart mongod
```

Start MongoDB
```bash
sudo systemctl start mongod
```
### Checking MongoDB status

```bash
sudo systemctl status mongod

```
### Change config
You can change config also through running:
```bash
sudo vi /etc/mongod.conf
```

