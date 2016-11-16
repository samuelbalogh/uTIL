# uTIL
**Micro TILs and utilities for macOS**

--- 

## Terminal commands

### Network

- Flush DNS

        $ sudo dscacheutil -flushcache
        
- Edit hosts file (to manually override DNS servers)

        $ sudo nano ./etc/hosts

- Start a simple HTTP server with Python

        $ python -m SimpleHTTPServer


### Troubleshooting

- List applications by memory usage

        $ top -o MEM
        
- List disk I/O and CPU load

        $ iostat

### Misc

- Run last command as root

        $ sudo !!

- Go to home dir 

        $ cd

- Edit aliases, PATH and other variables

        $ sudo nano .bash_profile
        $ source .bash_profile

### Python

- Open Python script in interactive mode (runs script and stays in the interpreter, preserving namespace)

        $ python -i [filename]

## Git (CLI)

#### Workflow

*This works for basic setups, however, the recommended workflow should always be discussed with the team*

1. (optional) Get the latest version of the branch from remote with `git fetch` (does not merge!)  
2. Get & merge the latest version of the remote branch with `git pull`  
3. Create a branch to work on & move to the new branch with `git checkout -b <branch>`  
4. Work and commit as usual  
5. Pull and merge the originating branch to avoid merge conflicts  
6. Create pull request  


##### Get info

`git branch` shows existing branches & which branch we are working on  
`git branch -a` shows remote branches too  
`git s` or `git status` shows files changed since last commit & whether they are included in the next commit  
`git diff` shows the changes in each file compared to the last commit  
`git blame <file>` shows who edited each line  
`git show HEAD` shows the last commit (author, date, message, diff)

##### Move around

`git checkout <branch>` move to another branch  
`git checkout -b <branch>` move to another branch, and if it doesn't exist, create a new one

##### Add things

`git add <file or path>` add a file or path to be included in the next commit (wildcards work for paths too, e.g. `git add src/scripts/*`)  
`git add .` or `git add -A` or `git add --all` add everything  
`git reset HEAD <file>` revert changes in a file to last commit

##### Clean up

`git branch -D <branch name>` delete branch

##### Stash (cut & paste)

`git stash` remove all changes since last commit & put them on a clipboard (useful e.g. if you want to merge master before a PR)  
`git stash show -p` view the contents of the stash (looks like a git diff)  
`git stash pop` apply the stashed changes again  
`git diff stash@{0}^1 stash@{0} -- <filename> | git apply` only apply the changes from one specific file from the stash  
`git stash list` show the contents of the stash (pop pops the latest, `stash@{0}`)  
`git stash clear` empty the stash

#### Extras & Extensions

##### Shortcuts

- Set short aliases to frequently used commands, e.g. `git chdev` = `git checkout develop`

        git config --global alias.chdev 'checkout develop'

- List existing aliases

        git config --global -l


##### Preview Github Readme.md file locally
  - Install [grip](https://github.com/joeyespo/grip): `$ pip install grip`
  - In the folder of the repo, type `$ grip`
  - Visit `http://localhost:6419/` in your browser

##### Generate an SSH Public Key

1. Check if an SSH key pair exists already

        $ cd ~/.ssh
        $ ls

  If `<key_name>` and `<key_name>.pub` are there, skip to step 3.

2. If no key found, generate one

        $ ssh-keygen

3. Check the contents of the public (`.pub`) key

        $ cat <key_name>.pub

4. Copy the all of the contents of the public key, go to [Github > Settings > SSH and GPG keys](https://github.com/settings/keys), click 'New SSH key' and paste the contents of the public key.
