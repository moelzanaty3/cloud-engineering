# DevOps Pre-Requisite Course

## Linux Commands

> 💡 The **terminal** is a command-line interface that allows you to interact with your system. It's an essential tool for
DevOps engineers because it lets you control your system and execute tasks efficiently without needing a graphical
interface.

### Basic

```bash
# Print 'Hi Mom' to the terminal
echo "Hi Mom" 

# List files and directories in the current directory
ls 

# List files with details (permissions, size, date modified)
ls -l 

# List all files, including hidden files (starting with '.')
ls -a

# Change to the directory 'my_dir'
cd my_dir 

# Go back to the previous directory
cd - 

# Print the current working directory 
pwd  # Example: ~/Desktop/my_dir

# Create and navigate into a new directory, 
# then print the current directory path
cd new_dir; mkdir www; pwd 
```

### Directories

```bash
# Create a new directory called 'my_dir'
mkdir my_dir 

# Create a nested directory structure, 'my_dir/work'
mkdir -p ~/Desktop/my_dir/work 

# Recursively remove the directory 'my_dir' and its contents
rm -r ~/Desktop/my_dir 

# Prompt for confirmation before deleting each file in 'my_dir'
rm -ri ~/Desktop/my_dir 

# Recursively copy 'my_dir' and its contents to 'my_copied_dir'
cp -r my_dir ~/Desktop/my_copied_dir 

# Move 'my_dir' to the 'Documents' folder
mv my_dir ~/Documents/
```

### Files

```bash
# Create an empty file called 'file.txt'
touch file.txt 

# Create multiple empty files in one command
touch file1.txt file2.txt file3.txt

# Create a file and add content in one step using 'cat' (Ctrl+D to end input)
cat > file.txt  
# Example input:
This is some sample content
# Ctrl+D to finish

# Append content to an existing file
echo "Additional content" >> file.txt

# Display the contents of 'file.txt'
cat file.txt 

# View contents of 'file.txt' with line numbers
cat -n file.txt 

# Copy 'file.txt' to 'copy_file.txt'
cp file.txt copy_file.txt 

# Rename or move 'file.txt' to 'sample_file.txt'
mv file.txt sample_file.txt 

# Delete 'sample_file.txt'
rm sample_file.txt 

# View the first 10 lines of 'file.txt'
head file.txt 

# View the last 10 lines of 'file.txt'
tail file.txt 

# Display file content in real-time (useful for logs)
tail -f file.txt
```

### User Account

```bash
# Displays the current logged-in user.  
whoami

# Show current user and their group information
id 

# Switch to another user 'moelzanaty3' (requires password)
su moelzanaty3

# Access a remote system using SSH
ssh moelzanaty@192.168.1.1

# Change the password for the current user
passwd 

# Run a command as the root user (administrator privileges)
sudo command

# Create a new user (requires sudo privileges)
sudo useradd new_user 

# Delete a user and their home directory
sudo userdel -r new_user 

# Add 'new_user' to the 'sudo' group (grant admin rights)
sudo usermod -aG sudo new_user
```

> 💡 **What is `sudo`?**: `sudo` stands for "superuser do." It allows regular users to run commands with administrative (
root) privileges, useful for performing system-wide tasks.

### Downloading Files

```bash
# Download a file from a URL using 'curl' (save to current directory)
curl -O https://example.com/file.txt  # -O saves with the original filename

# Download a file and save it as 'new_file.txt'
wget https://example.com/file.txt -O new_file.txt

# Download a file in the background using 'wget'
wget -b https://example.com/largefile.zip
```

### Permissions

```bash
# Change the permissions of 'file.txt' to read, write, and execute for the owner
chmod 700 file.txt

# Give read and write permissions to the owner, and read-only to the group and others
chmod 644 file.txt

# Change the owner of 'file.txt' to 'moelzanaty'
chown moelzanaty file.txt

# Change the owner and group of 'file.txt' to 'moelzanaty'
chown moelzanaty:moelzanaty file.txt

# Change ownership of all files in a directory
chown -R moelzanaty ~/my_dir
```

| Command | Description                                                                                                                          |
|---------|--------------------------------------------------------------------------------------------------------------------------------------|
| `chmod` | Change file permissions. For example, `chmod 755 myfile` gives the owner full permissions and everyone else read and execute access. |
| `chown` | Change file ownership. E.g., `sudo chown user:group myfile`.                                                                         |

💡 **Understanding File Permissions**:
    - Permissions are represented as three sets of characters: for the **owner**, **group**, and **others**.
        - `r` = read, `w` = write, `x` = execute.
        - The numbers represent permissions: `7` = read, write, and execute (rwx), `5` = read and execute (rx).
        - For example, `chmod 700 file.txt` allows **only the owner** to read, write, and execute the file.

### System Information

```bash
# Check the OS version
cat /etc/*release*

# Check the kernel version
uname -r

# Show system architecture
uname -m

# Display system uptime
uptime

# Display disk usage (with human-readable sizes)
df -h

# Display running processes
top 

# Display detailed information about CPU and memory usage
htop  # (may need to install htop using `sudo apt install htop`)
```

## Vim

a highly configurable text editor used by developers, sysadmins, and cloud engineers. It’s included by
default on most Linux distributions, making it a crucial tool for anyone working with cloud infrastructure, scripting,
or automation.

While Vim can feel overwhelming at first, it is incredibly powerful once you master it. This guide will introduce you to
basic concepts, essential commands, and resources to help you quickly become proficient.

### Why Cloud Engineers Should Learn Vim

As a cloud engineer, you’ll often need to work with text files like configuration files, scripts, and logs on remote
servers. Vim allows you to efficiently edit files directly from the terminal without needing a graphical user interface,
making it invaluable when dealing with headless systems or remote environments.

---

### Learn Vim

Here are some resources to get you started on your Vim journey:

1. [Seven habits of effective text editing](http://www.moolenaar.net/habits.html)
2. [The Way of the Vim Warrior](https://github.com/dahu/LearnVim)
3. [Learn Vimscript the Hard Way](http://learnvimscriptthehardway.stevelosh.com/)
4. [Learning Vim (Chinese)](https://github.com/dofy/learn-vim)
5. [Vim Adventures](http://vim-adventures.com/)
6. [Vim Doctor](https://github.com/adembudak/vim-doctor)
7. [Vim Genius](http://www.vimgenius.com/)
8. [Vim Tips](http://zzapper.co.uk/vimtips.html)
9. [Fortune vimtips](https://github.com/hobbestigrou/vimtips-fortune)
10. [Vim Galore](https://github.com/mhinz/vim-galore)
11. [PacVim](https://github.com/jmoon018/PacVim)

> 💡 **Learning Tip**: Try **Vim Adventures** (a fun game) to practice and get comfortable with Vim commands.

### Basic Vim Commands

Here are some essential commands that will help you navigate and edit files in Vim:

| Command         | Description                                                   |
|-----------------|---------------------------------------------------------------|
| `vim filename`  | Open a file in Vim.                                           |
| `i`             | Enter **insert mode** to start editing text.                  |
| `Esc`           | Exit **insert mode** and go back to command mode.             |
| `:w`            | Save the file.                                                |
| `:q`            | Quit Vim.                                                     |
| `:wq`           | Save and quit.                                                |
| `:q!`           | Quit without saving changes.                                  |
| `dd`            | Delete the current line.                                      |
| `yy`            | Copy the current line (yank).                                 |
| `p`             | Paste the copied text.                                        |
| `/pattern`      | Search for a word or pattern in the file.                     |
| `n`             | Jump to the next occurrence of the search pattern.            |
| `u`             | Undo the last change.                                         |
| `Ctrl + r`      | Redo the last undone change.                                  |
| `gg`            | Go to the top of the file.                                    |
| `G`             | Go to the bottom of the file.                                 |
| `:set nu`       | Show line numbers.                                            |
| `:set nonu`     | Hide line numbers.                                            |
| `%s/old/new/g`  | Find and replace all occurrences of 'old' with 'new'.         |
| `:sp filename`  | Split the screen and open a file in the new split.            |
| `:vsp filename` | Vertically split the screen and open a file in the new split. |
| `Ctrl + w + w`  | Switch between split screens.                                 |
| `:help`         | Open Vim's help documentation.                                |

---

### Useful Tips

- **Modes in Vim**: Vim operates in different modes—**insert mode** (where you edit text) and **command mode** (where
  you give commands). Use `i` to enter insert mode, and `Esc` to return to command mode.

- **Exiting Vim**: Many new users struggle with exiting Vim. Remember, `:q!` will quit without saving, while `:wq` saves
  and quits.

- **Search and Replace**: You’ll frequently need to search for specific terms in configuration files. Use `/` to search,
  and `%s/old/new/g` to replace text globally.


---

## Package Managers

Package management involves a set of tools that automate the process of installing, upgrading, configuring, and removing
software packages for an operating system in a consistent and efficient manner.

CentOS utilizes **RPM (Redhat Package Manager)** and **YUM (Yellowdog Updater Modified)** for package management.

### RPM

RPM is a low-level package manager that allows you to install, remove, and query individual packages. However, RPM does
not handle package dependencies.

```bash 
# Install a package
rpm -i package.rpm

# Remove a package
rpm -e package

# Query if a package is installed
rpm -q package

# List all installed packages
rpm -qa

# Query detailed information about a package
rpm -qi package
```

The main drawback of RPM is its inability to resolve package dependencies automatically. This limitation led to the
development of YUM.

### YUM

YUM is a higher-level package manager that resolves dependencies automatically. It uses RPM under the hood but
simplifies package management by checking and installing all necessary dependencies.

#### How does YUM find dependencies?

YUM relies on repositories to locate and retrieve dependencies. Repository information is stored in the
`/etc/yum.repos.d/` directory. Each operating system version has its own set of repositories. For instance, when you run
`yum install httpd`, YUM searches these repositories to find the `httpd` package and its dependencies.

#### Installing packages not available in default repositories

If a package is not available in the default repositories, you can manually add a repository by placing its
configuration file in the `/etc/yum.repos.d/` directory. Once the repository is added, you can use
`yum install package_name` to install the package.

#### Common YUM Commands

```bash
# Display a list of available repositories
yum repolist

# List files in /etc/yum.repos.d/ to see available repositories
ls /etc/yum.repos.d/

# Get detailed information about a specific repository
yum repoinfo repository_name 
# or
cat /etc/yum.repos.d/repository_name.repo

# List installed packages
yum list installed

# Install a package
yum install package_name

# Remove a package
yum remove package_name

# Update a specific package
yum update package_name

# Update all packages on the system
yum update

# Search for a package by name or description
yum search package_name

# Show detailed information about a package
yum info package_name

# Clean YUM cache (useful when troubleshooting)
yum clean all

# Check for available updates without installing
yum check-update
```

### Homebrew

On macOS, **Homebrew** is the most popular package manager. It simplifies the process of installing and managing
software by automating the installation and updating of packages.

#### Installing Homebrew

To install Homebrew, use the following command in your terminal:

```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

#### Common Homebrew Commands

```bash
# Update Homebrew and its formulae
brew update

# Install a package (called a "formula")
brew install package_name

# Remove a package
brew uninstall package_name

# List installed packages
brew list

# Upgrade an installed package
brew upgrade package_name

# Upgrade all packages
brew upgrade

# Search for a package by name or description
brew search package_name

# Show detailed information about a package
brew info package_name

# Clean up old versions of installed packages
brew cleanup

# Check for potential issues in your Homebrew setup
brew doctor
```

Homebrew also supports casks, which are used to install macOS applications directly.

```bash
# Install a macOS app using Homebrew Cask
brew install --cask app_name

# List installed cask applications
brew list --cask

# Uninstall a macOS app installed via cask
brew uninstall --cask app_name
```


| Command           | Description                                                      |
|-------------------|------------------------------------------------------------------|
| `apt-get install` | Install a package using the APT package manager (Debian/Ubuntu). |
| `yum install`     | Install a package using YUM (Red Hat-based distros).             |
| `brew install`    | Install a package using Homebrew (for macOS and Linux).          |

> 💡 **Tip**: When switching between different Linux distributions or macOS, you may encounter different package managers (
APT, YUM, Homebrew). Each serves the same purpose but has its syntax and ecosystem of packages.

## Services

Services are programs that run in the background and provide specific functionality to the operating system or users.
Managing services involves controlling their lifecycle: starting, stopping, enabling them to start at boot, disabling
them, and checking their status.

### Linux (CentOS, Ubuntu, etc.)

Linux systems provide two main utilities for managing services: `service` (older) and `systemctl` (modern).

#### Service Management Commands

```bash
# Start the SSH service
service sshd start  # Older command

# Alternative command to start the SSH service (modern)
systemctl start sshd  # Preferred for modern Linux distros using systemd

# Stop the SSH service
systemctl stop sshd

# Restart the SSH service
systemctl restart sshd

# Check the status of the SSH service (e.g., is it running, any errors?)
systemctl status sshd

# Enable the SSH service to start automatically at boot
systemctl enable sshd

# Disable the SSH service from starting automatically at boot
systemctl disable sshd
```

**Note**: `systemctl` is the modern tool and part of `systemd`, which most modern Linux distributions use. Some older
systems (like CentOS 6) may still rely on the `service` command and use `init.d`.

#### Checking Available Services

You can list all active services with:

```bash
systemctl list-units --type=service
```

To view all services (active, inactive, etc.):

```bash
systemctl list-units --all --type=service
```

#### Creating a New Service (Linux Example)

To create a custom service, you need to define a **systemd service unit file**. Here's how you can do it.

##### Create the Service File

Create a file in `/etc/systemd/system/` with a `.service` extension (e.g., `my_custom_service.service`).

```bash
sudo nano /etc/systemd/system/my_custom_service.service
```

##### Define the Service Configuration

Add the following contents to define your service:

```ini
[Unit]
Description=My Custom Service
After=network.target  # Ensure network is up before starting

[Service]
ExecStart=/usr/bin/my_custom_script.sh  # Path to your script
Restart=always  # Restart automatically if the service crashes

[Install]
WantedBy=multi-user.target
```

- `Description`: A brief description of what the service does.
- `After`: This ensures the service starts only after certain dependencies (like networking) are ready.
- `ExecStart`: The path to the script or executable that the service will run.
- `Restart`: `always` ensures the service restarts if it crashes.
- `WantedBy`: Determines the run-level at which the service will start. `multi-user.target` is typical for most
  services.

##### Reload Systemd and Start the Service

Once the file is created, reload `systemd` so it recognizes the new service:

```bash
sudo systemctl daemon-reload
```

Start the service manually for the first time:

```bash
sudo systemctl start my_custom_service
```

Enable the service to start at boot:

```bash
sudo systemctl enable my_custom_service
```

##### Check the Status

You can check the status or logs of your custom service with:

```bash
sudo systemctl status my_custom_service
```

### macOS

macOS uses `launchd` and `launchctl` for managing services. The commands to manage services in macOS are a bit
different, but the core idea remains the same.

#### Service Management Commands

```bash
# Start a service
sudo launchctl load /Library/LaunchDaemons/com.yourservice.plist

# Stop a service
sudo launchctl unload /Library/LaunchDaemons/com.yourservice.plist

# Enable a service to start at boot
sudo launchctl load -w /Library/LaunchDaemons/com.yourservice.plist

# Disable a service from starting at boot
sudo launchctl unload -w /Library/LaunchDaemons/com.yourservice.plist
```

macOS uses **property list files (.plist)** to define services, located in `/Library/LaunchDaemons` (for system-wide
services) or `~/Library/LaunchAgents` (for user-specific services). These `.plist` files define when and how services
should start.

#### Creating a New Service

In macOS, services are defined in **.plist** files. Here's how to create a custom service on macOS:

##### Create the Service File

Create a new file in `/Library/LaunchDaemons/` (for system-wide services) or `~/Library/LaunchAgents/` (for
user-specific services).

```bash
sudo nano /Library/LaunchDaemons/com.mycustom.service.plist
```

##### Define the Service Configuration

Add the following XML to the file:

```xml
<?xml version="1.0" encoding="UTF-8"?>
<plist version="1.0">
    <dict>
        <key>Label</key>
        <string>com.mycustom.service</string>
        <key>ProgramArguments</key>
        <array>
            <string>/usr/local/bin/my_custom_script.sh</string> <!-- Path to your script -->
        </array>
        <key>RunAtLoad</key>
        <true/> <!-- Start service at boot -->
        <key>KeepAlive</key>
        <true/> <!-- Restart automatically if it crashes -->
    </dict>
</plist>

```

- `Label`: A unique identifier for the service.
- `ProgramArguments`: The path to the script or command the service runs.
- `RunAtLoad`: If `true`, the service runs automatically when loaded.
- `KeepAlive`: Ensures the service restarts if it crashes.

##### Load the Service

Once you've saved the `.plist` file, load the service:

```bash
sudo launchctl load /Library/LaunchDaemons/com.mycustom.service.plist
```

Enable it to start at boot:

```bash
sudo launchctl load -w /Library/LaunchDaemons/com.mycustom.service.plist
```

##### Check the Service

To check if your service is running:

```bash
sudo launchctl list | grep com.mycustom.service
```
