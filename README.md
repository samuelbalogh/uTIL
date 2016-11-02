# uTIL
**Micro TILs and utilities**

---

## Terminal commands

- Flush DNS on macOS

        $ sudo dscacheutil -flushcache

- Start a simple HTTP server with Python

        $ python -m SimpleHTTPServer

- List applications by memory usage

        $ top -o MEM

- Go to home dir 

        $ cd

- Edit aliases, path and other variables

        $ sudo nano .bash_profile

- Open Python script in interactive mode (runs script and stays in the interpreter, preserving namespace)

        $ python -i [filename]
        
- Preview Github Readme.md file locally 
    - Install [grip](https://github.com/joeyespo/grip): `$ pip install grip`
    - In the folder of the repo, type `$ grip`
    - Visit `http://localhost:6419/` in your browser