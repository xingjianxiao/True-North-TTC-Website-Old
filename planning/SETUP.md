# Instructions

## How to Set Up and Use Github

### create github account

### install git 
- install git [here](https://www.atlassian.com/git/tutorials/install-git#windows)

### install vscode 
- install vscode [here](https://code.visualstudio.com/download)

### create folder
- this folder will hold your github repository locally on your machine

### set up ssh private key
- you will not be able to clone a private repository if you do not have the private key

-open vscode terminal

- type `ssh-keygen -t rsa -C "myemail@gmail.com"` 

- your private key is the location without the .pub

- type `ssh-add ~/.ssh/id_rsa` or whatever your path is

- type `ssh-agent -s` if the previous line did not work

- if still not working, set ssh agent to manual

    - run windows powershell as administrator

    - `Get-Service ssh-agent`

    - `Get-Service ssh-agent | Select StartType`

    - if StartType is disabled, use `Get-Service -Name ssh-agent | Set-Service -StartupType Manual`

    - check again using `Get-Service ssh-agent | Select StartType`

    - retry previous steps and ssh agent should start

- open private key using `cat ~/.ssh/id_rsa.pub`

- copy the private key

### add private key to github
- open github

- go to profile settings

- click on SSH and GPG keys

- paste your private key

- add SSH key

### clone private repository
- copy public ssh key

- type `git clone "ssh key"` into vscode terminal

- should begin cloning

### setting up your identity
- set your name using `git config --global user.name "Eric Chen"`

- set your email using `git config --global user.email "ericchen12354@gmail.com"`
