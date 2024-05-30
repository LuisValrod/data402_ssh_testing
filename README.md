# data402_ssh_testing
Repo for testing ssh keys and github


## Steps to set up your ssh connection

- Go to your .ssh directory : `cd .ssh`
  - If you don't have that directory, make it: `mkdir .ssh`
- Once in the directoy run the following command: `ssh-keygen -t rsa -b 4096 -C "youremail@mailserver.com"`
  - You'll be asked for the name of the file   
- It is always advisable to run `ls` so that you can see the name of you ssh key.
- Then run: `cat your_key.pub`
  - This will provide a public key
<br>

- **If you are setting up a connection with GitHub follow the next steps**:
  - Go to your repository
  - Settings
  - Deployment Keys
  - Add new Key
  - Type the name of the key
  - Copy and paste the key that you got from the command `cat your_key.pub` described previously
  - Clik on "allow write" box

<br>

- Now travel to the directory where you want to set up your repository
- Test that the connection will work with the following commands:
  - `eval ssh-agent`
  - `ssh-add ~/.ssh/git_test_key`
  - `ssh -T git@github.com`
This steps will give youa message like the following: `Hi LuisValrod/data402_ssh_testing! You've successfully authenticated, but GitHub does not provide shell access.`

**It might be necessary to confirm that you want to carry on with the process since you might receive a warning message before completing this step. In that case, simply type "yes"**
- Finally, run the `git clone` command with the ssh link availabe in your github

  
