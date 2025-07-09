# MODULE 5.0: THE UNIX COMMAND LINE — Bash, Files, Installations

#### 1. Basic Bash Commands (Terminal Essentials)

| Command           | Purpose                                 |
| ----------------- | --------------------------------------- |
| `pwd`             | Print working directory (where you are) |
| `ls`              | List files and directories              |
| `cd folder/`      | Change directory                        |
| `cd ..`           | Go up one level                         |
| `mkdir newFolder` | Create a new folder                     |
| `touch file.txt`  | Create a new empty file                 |
| `rm file.txt`     | Delete a file                           |
| `rm -r folder/`   | Delete a folder recursively             |
| `cp file1 file2`  | Copy file1 to file2                     |
| `mv file1 new/`   | Move file1 to `new/` folder             |
| `clear`           | Clear terminal screen                   |

---

#### 2. File & Folder Manipulation without GUI

These commands allow full control over the filesystem directly from terminal:

* **Create structure:**

  ```bash
  mkdir projects
  cd projects
  touch index.html style.css app.js
  ```

* **Edit files (CLI-based editors):**

  ```bash
  nano file.txt     # lightweight editor
  vim file.txt      # advanced (for experienced users)
  ```

* **Check file content:**

  ```bash
  cat file.txt      # show file content
  head file.txt     # show first 10 lines
  tail file.txt     # show last 10 lines
  ```

---

#### 3. Download and Install via Command Line

**Install packages (Ubuntu/Debian-based systems):**

```bash
sudo apt update
sudo apt install nodejs
sudo apt install npm
```

**Using `curl` or `wget`:**

```bash
curl -O https://example.com/file.zip
wget https://example.com/file.zip
```

**Unzip and Extract:**

```bash
unzip file.zip
tar -xvzf file.tar.gz
```

**Give execute permission & run:**

```bash
chmod +x script.sh
./script.sh
```

---

### Summary

| Area              | Focus                                 |
| ----------------- | ------------------------------------- |
| Bash Basics       | `pwd`, `ls`, `cd`, `mkdir`, `touch`   |
| File Manipulation | `rm`, `cp`, `mv`, `nano`, `cat`       |
| Installations     | `apt`, `wget`, `curl`, `chmod`        |
| Purpose           | Speed, control, scripting, remote use |

<footer>TO BE CONT...</footer>
