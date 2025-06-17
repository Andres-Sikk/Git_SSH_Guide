# SSH guide for Windows 10, Git Bash and Github:
https://www.toolsqa.com/git/git-tutorial/. \
https://www.toolsqa.com/git/ssh-protocol/. \
(in Git Bash copy = Control + Insert ,paste = Shift + Insert)

## SSH service in Windows:
(you need administrator password!) \
Type "services" into windows search and open it \
Find OpenSSH Authentication Agent -> right click -> properties -> change startup type to "automatic" -> click "start" button -> wait a few seconds and click OK

## Create SSH key:
(optional?) Type into Git Bash: eval $(ssh-agent -s) \
(optional?) agent pid "1234" = ssh-agent is working \
Type into Git Bash: ssh-keygen -t ed25519 -C "Desktop_1_SSH" (“Desktop_1_SSH” can be any file name) \
Press ENTER three times (leave everything blank) \
(optional?) Type into Git Bash: ls -l ~/.ssh \
open id_ed25519.pub (in C:\Users\%USERNAME%\.ssh\) (or whatever the filename of *.pub is) with notepad and copy contents \
Go to github account settings -> SSH and GPG keys -> Press "New SSH key" button -> paste key into "key" field, choose title name -> press "Add SSH Key" button \
(optional?) Type into Git Bash: ssh -T git@github.com \
Type yes and press enter \
(optional?) Hi "Github username"! You've successfully authenticated, but GitHub does not provide shell access. = SSH is working

## SSH clone repo:
Go to your repo (you must be logged in to Github) -> click "Code" button -> under "Clone" click "SSH" and copy your repo url \
Type into Git Bash: git clone "YOUR REPO URL" \
If you get a message "Please tell me who you are": \
Type into Git Bash: git config --global user.email "git@github.com" \
Type into Git Bash: git config --global user.name "YOUR GITHUB USERNAME"