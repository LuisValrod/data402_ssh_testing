# Install mongoDB on AWS ec2

### Go to ssh from terminal
```bash
cd .ssh
```
### To determine version of mongo
```bash
cat /etc/lsb-release
```
### Importing Mongo Public GPG Key
```bash
curl -fsSL https://www.mongodb.org/static/pgp/server-7.0.asc | \
   sudo gpg -o /usr/share/keyrings/mongodb-server-7.0.gpg \
   --dearmor
```

### Create list file in MongoDB

```bash
echo "deb [ arch=amd64,arm64 signed-by=/usr/share/keyrings/mongodb-server-7.0.gpg ] https://repo.mongodb.org/apt/ubuntu jammy/mongodb-org/7.0 multiverse" | sudo tee /etc/apt/sources.list.d/mongodb-org-7.0.list
```

### Connect with your virtual computer(ec2)
```bash
ssh -i "your----.pem" ubuntu@ec0-00-0000.eu-central-1.compute.amazonaws.com
```

### Reload local packages
```bash
sudo apt-get update
```

### Install MongoDB Packages
```bash
sudo apt-get install -y mongodb-org
```

### Install MongoDB
follow the steps for installation
```bash
https://www.mongodb.com/docs/manual/tutorial/install-mongodb-on-ubuntu/
```


### Config issue
```bash
sudo nano /etc/ssh/sshd_config
//or
sudo vi /etc/mongod.conf
```
```commandline
press : 'i'
change bindIP : 0.0.0.0
security : authorization: enabled
press : 'esc' on your key board
type : Ctrl + o
type : Ctrl + x
```
### Stop Mongo
```bash
sudo systemctl stop mongod
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

