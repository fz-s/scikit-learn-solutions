# set-up instructions
## 1. initial GIT set-up (based on the privacy settings)
### a. Switch to SSH URL for your repository: Change the remote URL to SSH by running:
git remote set-url origin git@github.com:<user-name>/<repository-name>.git
### b. (one-time) GitHub provides a special no-reply email address that you can use for commits, which will prevent your actual email address from being exposed.
git config --global user.email <git provided email from settings/emails>
### c. run SSH Agent, add key and authenticate using passphrase
eval $(ssh-agent -s)
ssh-add ~/.ssh/id_rsa <!-- your keyname may vary -->
ssh -T git@github.com

## d. (one-time) register your venv as default jupyter kernel
cd /path/to/your/git/repo
source /path/to/your/env/bin/activate
pip install ipykernel
python -m ipykernel install --user --name=myenv 

### e. lauch vs code from the terminal
### f. (one-time) ensure that settings (json) contains this entry
"git.ssh.path": "/usr/bin/ssh"

## 2.  to create a new repository on the command line
echo "# statistics-using-python" >> README.md
git init
git add README.md
git commit -m "first commit"
git branch -M main
git remote add origin https://github.com/fz-s/statistics-using-python.git
git push -u origin main

## 3. to push an existing repository from the command line
git remote add origin https://github.com/fz-s/statistics-using-python.git
git branch -M main
git push -u origin main

## 4. select venv's python interpreter 
command palette -> select python interpreter --> navigate and select the python3 file within your environment's bin directory
