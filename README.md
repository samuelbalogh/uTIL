# uTIL
**Micro TILs and utilities**

---

## Terminal commands

### Network

- Flush DNS on macOS

        $ sudo dscacheutil -flushcache
        
- Edit hosts file (to manually override DNS servers)

        $ sudo nano ./etc/hosts

- Start a simple HTTP server with Python

        $ python -m SimpleHTTPServer


### Troubleshooting

- List applications by memory usage

        $ top -o MEM

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

### Github

- Preview Github Readme.md file locally
    - Install [grip](https://github.com/joeyespo/grip): `$ pip install grip`
    - In the folder of the repo, type `$ grip`
    - Visit `http://localhost:6419/` in your browser