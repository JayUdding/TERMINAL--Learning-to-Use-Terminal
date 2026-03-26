TERMINAL--Learning-to-Use-Terminal

The Top file (Commands Reference File) is a list of the commands for Terminal and some example uses for memorization and practice.
Use this file (with or without AI) to create quizzes to memorize and practice the prompts. Learn to use examples of navigating within Terminal with ease and then get ready to build some basic python programs that can be run directly in Terminal.

Useful tools besides the Reference File:

Flashcards
Cheatsheet

**Interactive shell script**: Write a simple shell script that presents you with a series of Terminal commands and asks you to type them in. You can use a tool like `read` or `dialog` to create an interactive prompt.

**Terminal-based game**: Create a simple game that tests your knowledge of Terminal commands. For example, you can write a script that generates a random command and asks you to type it in correctly.

Some popular tools and platforms for creating these types of projects include:

* **Anki**: A popular flashcard app that uses spaced repetition to help you memorize information.
* **Quizlet**: A study app that offers flashcards, tests, and study games for a wide range of subjects, including Terminal commands.
* **GitHub Gist**: A platform for sharing and collaborating on code snippets, including shell scripts and Terminal commands.
* **Markdown editors**: Tools like Mou, Typora, or Bear that allow you to create and edit Markdown documents.
* **Shell scripting tools**: Tools like Bash, Zsh, or Fish that allow you to write and run shell scripts.

Remember, the most important thing is to choose a format and tool that works for you and your learning style. Good luck and have fun learning Terminal commands!

Sample Quizzes:

 

Ready for another beginner quiz — no hints unless you ask. Reply with the command you'd type.

Question 1/10:
What command creates an empty file named todo.txt?

Question 2/10:
What command copies a directory named src and all its contents to src_backup?

Question 3/10:
What command removes an empty directory named temp?

Question 4/10:
What command force-removes a directory named old_project and everything inside it?

Question 5/10:
What command prints the full path of the current working directory?

Question 6/10:
What command counts the number of lines in a file named notes.txt?

Question 7/10:
What command searches recursively for the string TODO in the current directory and prints matching lines?

Question 8/10:
What command writes the output of ls into a file named listing.txt, replacing any existing content?

Question 9/10:
What command sets a file named report.txt to have permissions rw-r--r-- (owner read/write, group and others read)?

Question 10/10:
What command prints the value of the PATH environment variable?

 
ls – list files
cd ~ – go to home
cd - – go back to previous directory
mkdir Test – make a directory
cp example.txt ~/Documents – copy a file
mv old.txt new.txt – rename a file
rm temp.txt – delete a file
cat notes.txt – display file contents
nano essay.txt – edit a file
clear – clear screen
 
Example Quiz

1. Which command shows the current working directory?
2. Which command lists files and directories in the current directory?
3. Which command changes the current directory to a specified path?
4. Which command creates a new empty file?
5. Which command creates a new directory?
6. Which command copies a file from one location to another?
7. Which command moves or renames a file or directory?
8. Which command removes (deletes) a file?
9. How do you redirect the standard output of a command into a file, overwriting the file?
10. Which command displays the manual (help) pages for other commands?

Answers provided: 1. cd 2. ls 3.  cd ./ 4. 5. 6. cp 7. mv 8. rm 9. mv 10. man
    
 Results (e.g.: 6 out of 10 correct):

 
1. Correct — `cd`
2. Correct — `ls`
3. Incorrect — `cd ./` only changes to the current directory. The general answer is `cd <path>` (e.g., `cd foldername` or `cd /path/to/dir`).
4. Missing / Incorrect — correct command: `touch` (creates a new empty file)
5. Missing / Incorrect — correct command: `mkdir` (creates a new directory)
6. Correct — `cp`
7. Correct — `mv`
8. Correct — `rm`
9. Incorrect — correct answer: use the redirection operator `>` (e.g., `command > file`) to overwrite a file\
10. 11. Correct — `man`
 
 Curriculum

  Here is the corrected, rigorous syllabus. No NOSTR. No multiple choice. Only drills that expose your specific failure modes until they become impossible.

---

# THE STOIC TERMINAL CURRICULUM
*For macOS Zsh Users with Zero Programming Knowledge*

**Premise:** The terminal is indifferent to your confusion. It responds only to precise inputs. You will not memorize 100 commands; you will master 15 until they are reflex. You will drill your errors—`cp` vs `mv`, `./` vs bare, `rm` vs `rmdir`—until you cannot mistake them.

**Rule:** If you stop to think about a command, you repeat it until it is muscle memory. Do not proceed to Week 2 until Week 1 is unconscious.

---

## WEEK 0: MUSCLE MEMORY & FILE OPERATIONS
**Goal:** Develop unconscious competence in navigation, file manipulation, and text editing. You cannot build software if you are fighting the editor.

**Critical Corrections from Your Errors:**
- `~` is your **home** directory (`/Users/you`). `/` is the **root** (system core). Confusing them will destroy your system.
- `rmdir` removes **empty directories only**. `rm` removes files. `rm -r` removes directories with contents.
- `cp` copies (duplicates). `mv` moves (relocates the original). If you `mv` a file, the original location no longer has it.
- `Ctrl+X` does **not** exit the terminal. It exits `nano`. To exit terminal: `exit` or `Ctrl+D`.
- `id -p` shows your numeric UID. Use `whoami` or `id -un` for your username.

### Daily Drills (10 minutes/day)

**Day 1: Navigation as Reflex**
Execute this sequence 10 times. Predict `pwd` output before hitting Enter.
```bash
cd /tmp && pwd
cd ~ && pwd
cd /usr/local/bin && pwd
cd - && pwd  # Toggles back to previous
cd - && pwd  # Toggles forward again
```
*Success:* You know where you are without looking at the prompt.

**Day 2: Path Resolution (The ./ Distinction)**
Create the structure, then execute each command. Observe that all five work, but understand why.
```bash
mkdir -p ~/week0_test/subdir && touch ~/week0_test/file.txt
cd ~/week0_test

ls file.txt        # Bare relative: "Look here"
ls ./file.txt      # Explicit relative: "Look explicitly here"  
ls ../week0_test/file.txt  # Parent traversal
ls ~/week0_test/file.txt   # Absolute: "Full address from home"
ls subdir/../file.txt      # Logical resolution (empty subdir doesn't matter)

cd ~ && rm -r week0_test
```
*Critical Insight:* `subdir/../file.txt` resolves to `file.txt` because paths resolve logically, not physically.

**Day 3: Nano Mastery (10 Repetitions)**
Do not proceed until your fingers know the keys without your brain.
```bash
nano ~/trash.txt
# Type: "This is a test"
# Press: Ctrl+O (Write Out), Enter (Confirm), Ctrl+X (Exit)
cat ~/trash.txt
nano ~/trash.txt  
# Delete all text (Backspace/Del), save, exit
rm ~/trash.txt
```
*Trap:* If you press `Ctrl+X` before saving, nano asks "Save modified buffer?" Press `n` to discard, `y` to save.

**Day 4: File Lifecycle (The cp vs mv Drill)**
Execute each step. Use `ls` after every command to verify state.
```bash
mkdir -p ~/week0_test/subdir
touch ~/week0_test/original.txt

# Copy creates a DUPLICATE
cp ~/week0_test/original.txt ~/week0_test/copy.txt
ls ~/week0_test/  # Should see BOTH original and copy

# Move relocates the ORIGINAL (no duplicate)
mv ~/week0_test/copy.txt ~/week0_test/subdir/moved.txt
ls ~/week0_test/  # copy.txt is GONE from here
ls ~/week0_test/subdir/  # moved.txt is here

# Cleanup
rm ~/week0_test/original.txt
rm ~/week0_test/subdir/moved.txt
rmdir ~/week0_test/subdir  # Must be empty first
rmdir ~/week0_test
```

**Day 5: Permissions (The x Bit)**
```bash
touch ~/perm_test.sh
ls -l ~/perm_test.sh    # Note: -rw-r--r-- (no x anywhere)

chmod +x ~/perm_test.sh # Add execute permission
ls -l ~/perm_test.sh    # Note: -rwxr-xr-x (x appears three times)

chmod -x ~/perm_test.sh # Remove execute
ls -l ~/perm_test.sh    # x is gone
rm ~/perm_test.sh
```
*Success:* You spot the `x` instantly in `ls -l` output. You understand `x` means "executable."

**Day 6: The Complete Loop (No Notes)**
Do not look at previous days. If you hesitate, restart.
```bash
mkdir -p ~/.local/bin
nano ~/.local/bin/mytest
# Type exactly:
# #!/bin/zsh
# echo "Success"

chmod +x ~/.local/bin/mytest
cd /tmp
mytest    # Should output "Success" (no ./ needed because ~/.local/bin is in PATH)
which mytest  # Shows /Users/you/.local/bin/mytest
rm ~/.local/bin/mytest
```

**Day 7: Assessment**
```bash
mkdir -p ~/week0_test/subdir
touch ~/week0_test/subdir/file.txt
cd /tmp && ls ~/week0_test/../week0_test/subdir/../../week0_test
# Expected output: subdir
rm -r ~/week0_test
```
*Success:* You predicted the output before typing.

### Week 0 Quiz

**Fill-in-the-Blank:**
1. The command to list files is _______.
2. The command to change to your home directory is _______.
3. The command to move up one directory level is _______.
4. The command to create a directory is _______.
5. The command to delete a file is _______.
6. The command to delete an **empty** directory is _______.
7. The command to copy a file is _______.
8. The command to move/rename a file is _______.
9. In `nano`, save by pressing _______ then _______.
10. In `nano`, exit by pressing _______.

**Scenario-Based:**
11. You type `rmdir photos` and get `rmdir: photos: Directory not empty`. What command should you have used instead? _______
12. You type `mv report.txt backup/` and now `report.txt` is gone from your current folder. Is this expected? _______ (Yes/No)
13. You type `cd /` and your prompt shows `/`. Are you in your home folder? _______ (Yes/No)
14. You type `myscript` and get `zsh: command not found`. You know the file exists in `~/.local/bin`. What is the likely problem? _______
15. You see `-rw-r--r--` in `ls -l`. Can you execute this file? _______ (Yes/No)

**Practical Exercise:**
16. Execute this sequence and report the final output: `cd /tmp && pwd && cd ~ && pwd && cd - && pwd`
17. Create a file `~/test.txt`, copy it to `~/Documents/test_copy.txt`, verify both exist with `ls`, then delete both.
18. Create a script `~/.local/bin/hello` that prints "Hello", make it executable, run it from `/tmp`, then delete it.

---

## WEEK 1: PATH MASTERY & ENVIRONMENT HYGIENE
**Goal:** Understand the difference between "where I am" (`pwd`) and "where my commands live" (`which`). Fix "command not found" errors without panic.

**Critical Concepts:**
- `$PATH` is a colon-separated list of directories where the shell searches for commands.
- Bare command (`ls`) = Search PATH. Relative (`./script`) = Look here only. Absolute (`/usr/bin/python3`) = Exact location.
- `export` sets environment variables for the current session. `~/.zshrc` makes them permanent.
- `which` shows you which binary executes when you type a command.

### Daily Drills

**Day 1: Admission Ticket**
Complete the Week 0 Day 6 exercise again, but this time intentionally break it:
1. Comment out your PATH line in `~/.zshrc` with `#`
2. Open new terminal
3. Type `mytest` → Observe `command not found`
4. Uncomment the line, `source ~/.zshrc` (or reopen terminal)
5. Verify it works

**Day 2: Location vs Execution**
```bash
mkdir -p ~/bin
cd ~/bin
nano whereami
# Add:
# #!/bin/zsh
# echo "Current: $(pwd)"
# echo "Script location: $0"

chmod +x ~/bin/whereami
cd /tmp && whereami
cd /usr/local/bin && whereami
```
*Observe:* `pwd` changes (where you stand), `$0` stays constant (where the file lives).

**Day 3: Permission Debugging**
```bash
chmod -x ~/bin/whereami
cd /tmp
whereami  # Should get "Permission denied"
ls -l ~/bin/whereami  # Observe missing x
chmod +x ~/bin/whereami  # Fix
```

**Day 4: Binary vs Script**
```bash
file ~/bin/whereami  # Should say "shell script"
file $(which ls)     # Should say "Mach-O 64-bit executable" (binary)
file $(which python3) # Binary
```
*Rule:* If `file` says "text", it's a script. If it says "executable" but `cat` shows garbage, it's a binary.

**Day 5: The Shebang**
Create two scripts:
1. `~/bin/test1` with first line `#!/bin/zsh`
2. `~/bin/test2` with first line `#!/bin/bash`
Both print "Hello". Make executable. Run both. Observe both work (macOS has both shells).

### Week 1 Quiz

**Fill-in-the-Blank:**
1. The command to show your current directory is _______.
2. The command to show where a command is located is _______.
3. The file to edit to make PATH changes permanent is _______.
4. To add `~/bin` to PATH, you write: `export _______="~/bin:$PATH"` (Note: Use correct variable expansion)
5. The symbol to run a script in the current directory is _______.

**Scenario-Based:**
6. You type `python3` and get `zsh: command not found`. What does this actually mean the shell did? _______
7. You type `./myscript` and get `Permission denied`. What is missing? _______
8. You installed a program but must type the full path `/opt/homebrew/bin/program` to run it. What file do you edit to fix this? _______
9. You see `drwxr-xr-x` in `ls -l`. What does the `d` indicate? _______
10. You see `-rwxr-xr-x`. What does the first `x` indicate? _______

**Practical Exercise:**
11. Create `~/bin/myecho`, make it executable, add `~/bin` to your `~/.zshrc` PATH, reload, and run `myecho` from `/tmp`.
12. Run `which python3` and `which ls`. Record the paths.
13. Execute: `echo $PATH | tr ':' '\n'` and count how many directories are searched for commands.

---

## WEEK 2: PYTHON DEVELOPMENT LOOP
**Goal:** Never touch system Python. Master virtual environments (isolation).

**Critical Concepts:**
- System Python (`/usr/bin/python3`) is for macOS. Do not install packages here.
- User Python (from python.org or Homebrew) is for general use.
- Virtual Environment Python is for projects (isolated).
- `python3 -m pip` ensures you use the pip matching your python3.
- **Never use `sudo pip`.**

### Daily Drills

**Day 1: The Isolation Test**
```bash
mkdir ~/project1 && cd ~/project1
python3 -m venv venv
source venv/bin/activate
which python3  # Should show ~/project1/venv/bin/python3
pip install requests
python3 -c "import requests; print('OK')"
deactivate
python3 -c "import requests"  # Should fail with ModuleNotFoundError
```

**Day 2: The Shebang in Python**
```bash
cd ~/project1
nano hello.py
# Type:
# #!/usr/bin/env python3
# import sys
# print(f"Python: {sys.executable}")
chmod +x hello.py
./hello.py  # Must use ./ because it's not in PATH
```

**Day 3: Multiple Projects**
Create `~/project2` with its own venv. Install a different package. Prove the two environments are separate.

### Week 2 Quiz

**Fill-in-the-Blank:**
1. To create a virtual environment: `python3 -m _______ venv`
2. To activate: `source _______/bin/activate`
3. To exit the environment: _______
4. To install packages inside the environment: `python3 -m _______ install <package>`
5. The prompt indicator showing you're in a venv is _______.

**Scenario-Based:**
6. You type `pip install flask` and get a permission error. What is the likely mistake? _______
7. Your prompt shows `(venv)`. What does this indicate? _______
8. You run `python3 -c "import requests"` outside the venv and it fails. Is this good or bad? _______
9. You are inside a venv and type `sudo pip install`. What have you done wrong? _______
10. You delete the `venv` folder. Are the packages gone? _______

**Practical Exercise:**
11. Create a project folder, create a venv, activate it, install `requests`, write a script that uses it, run it, deactivate, verify import fails outside.

---

## WEEK 3: ERROR DIAGNOSTICS & PERMISSIONS
**Goal:** Distinguish between PATH issues, permission issues, and syntax errors by sight. Read error messages without panic.

**Critical Errors to Master:**
- `command not found` → PATH issue or typo
- `Permission denied` → Missing `chmod +x` or wrong user
- `No such file or directory` → Typo in filename or wrong directory
- `EACCES` / `ENOENT` (in scripts) → Permission / File not found

### Daily Drills

**Day 1: Intentional Breakage**
Cause each error, then fix:
1. `chmod -x $(which python3)` then `python3` → Permission denied. Fix: `chmod +x`
2. `export PATH=""` then `ls` → Command not found. Fix: Restore PATH in new terminal.
3. `cd nonexistent` → No such file. Fix: `mkdir nonexistent` or correct typo.

**Day 2: The Reset**
Type `cat /bin/ls` (binary file). Terminal becomes garbled. Type `reset` and Enter to fix.

### Week 3 Quiz

**Scenario-Based:**
1. You type `myscript` and get `zsh: command not found`. Is this a PATH issue or permission issue? _______
2. You type `./myscript` and get `Permission denied`. What is missing? _______
3. You type `cd Documents` and get `No such file`. What are two possible causes? _______
4. You see `EACCES` in an error. What does this indicate? _______
5. You see `ENOENT`. What does this indicate? _______
6. You run a Python script and see `IndentationError`. Is this a terminal problem? _______
7. You type `cat binaryfile` and your terminal becomes garbled. What command fixes this? _______

**Practical Exercise:**
8. Create a script without `chmod +x`. Try to run it with `./`. Observe error. Fix with `chmod +x`.
9. Temporarily break your PATH by running `export PATH=""`. Try `ls`. Observe error. Open new terminal to fix.

---

## WEEK 4: VERSION CONTROL (Git)
**Goal:** Collaborate without panic. Understand SSH keys.

**Critical Concepts:**
- `git` is local version control. GitHub is remote hosting.
- `id_ed25519` (private key) stays on your machine. `id_ed25519.pub` (public key) goes to GitHub.
- `known_hosts` stores server identities (not your keys).

### Daily Drills

**Day 1: The SSH Key**
```bash
ssh-keygen -t ed25519 -C "you@example.com"
cat ~/.ssh/id_ed25519.pub  # Copy this to GitHub
```

**Day 2: The Clone**
```bash
git clone git@github.com:yourname/repo.git
cd repo
git status
```

**Day 3: The Loop**
Make change → `git add .` → `git commit -m "message"` → `git push`

### Week 4 Quiz

**Fill-in-the-Blank:**
1. To see what files changed: _______
2. To stage changes: _______
3. To save locally: _______
4. To upload to GitHub: _______
5. The public key file ends with: _______

**Scenario-Based:**
6. You type `git push` and get `Permission denied (publickey)`. What is likely wrong? _______
7. You see `<<<<<<< HEAD` in a file. What happened? _______
8. You type `git commit` and get "nothing to commit". What did you forget? _______

---

## WEEK 5: TEXT PROCESSING & PIPES
**Goal:** Combine commands. Search and filter.

**Commands:** `grep`, `find`, `|`, `>`, `>>`, `head`, `tail`, `wc`

### Week 5 Quiz

**Fill-in-the-Blank:**
1. To search for "error" in logs: _______
2. To count lines in a file: _______
3. To see first 10 lines: _______
4. To redirect output to file (overwrite): _______
5. To redirect output to file (append): _______

**Scenario-Based:**
6. You want lines 5-10 of a file. What pipeline? _______
7. You want to find all `.py` files. What command? _______

---

## WEEK 6: SHELL SCRIPTING
**Goal:** Automate tasks.

**Concepts:** Shebang (`#!/bin/zsh`), variables (`$1`, `$?`), `if`, `for`

### Week 6 Quiz

**Fill-in-the-Blank:**
1. First line of macOS Zsh script: _______
2. Make executable: _______
3. Run from current dir: _______
4. First argument variable: _______
5. Exit code of last command: _______

**Practical Exercise:**
6. Write a script that checks if a file exists, and prints "Found" or "Missing".

---

## WEEK 7: SYSTEM AWARENESS & HOMEBREW
**Goal:** Install software. Read manuals. Manage processes.

**Commands:** `brew`, `man`, `ps`, `top`, `kill`, `Ctrl+C`, `Ctrl+Z`

**Critical Distinction:** BSD (macOS) vs GNU (Linux) flags differ. Always check `man` pages.

### Week 7 Quiz

**Fill-in-the-Blank:**
1. To install software on macOS: _______
2. To read the manual: _______
3. To show running processes: _______
4. To stop a running process: _______
5. To suspend a process (background): _______

**Scenario-Based:**
6. You type `sed -i 's/old/new/' file` on macOS and get an error. Why? _______ (BSD sed requires different syntax than GNU)
7. You want to know what a command does without googling. What do you type? _______

---

## FINAL ASSESSMENT: THE READINESS CHECK

Execute flawlessly without notes:

1. Navigate to `/tmp`, create a file, edit it in nano, save, exit, return to home.
2. Create a Python venv, install a package, run a script using it, deactivate.
3. Clone a Git repo, make a commit, push it.
4. Diagnose a "command not found" error and fix it by editing `~/.zshrc`.
5. Explain the difference between `cp` and `mv`.
6. Explain why `./script` is needed but `ls` is not.

**Stoic Quote:**

*"First say to yourself what you would be; and then do what you have to do."* — Epictetus

 
 
